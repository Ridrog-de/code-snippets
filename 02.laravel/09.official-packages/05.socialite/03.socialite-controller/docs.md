---
title: 'Socialite Controller'
taxonomy:
    category:
        - docs
---

Der Controller für Sociallite

```
<?php

namespace App\Http\Controllers\Auth;

use Socialite;
use App\User;
use App\Social;
use App\Http\Controllers\Controller;

class SocialiteController extends Controller
{
    /**
     * Redirect the user to the GitHub authentication page.
     *
     * @return Response
     */
    public function redirectToProvider($provider)
    {
        if ($provider == 'twitch'){
            Socialite::with('twitch')->redirect();
        }

        return Socialite::driver($provider)->redirect();
    }

    /**
     * Obtain the user information from GitHub.
     *
     * @return Response
     */
    public function handleProviderCallback($provider)
    {
        $callback = Socialite::driver($provider)->user();

        $user = $this->createOrGetUser($provider, $callback);

        auth()->login($user);

        session()->flash('success', 'You are now logged in');

        return redirect()->to('/home');
    }

    public function createOrGetUser($provider, $callback)
    {
        $account = Social::where('provider', '=', $provider)->where('provider_id', '=', $callback->getId())->first();

        if ($account) {
            return $account->user;
        } else {

            $account = new Social([
                'provider_id' => $callback->getId(),
                'provider' => $provider,
            ]);

            $user = User::whereEmail($callback->getEmail())->first();

            if (!$user) {

                $name = $callback->getName();

                if(! $name){
                    $name = $callback->getNickname();
                }

                $user = User::create([
                    'email' => $callback->getEmail(),
                    'name' => $name,
                ]);
            }

            $account->user()->associate($user);
            $account->save();

            return $user;

        }

    }
}
```