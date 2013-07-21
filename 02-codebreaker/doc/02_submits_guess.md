## Feature: Code-breaker submits guess

You can review the feature file in this link [features/code-breaker_submits_game.feature](https://github.com/aleherse/katas-BDD/tree/master/02-codebreaker/features/features/code-breaker_submits_game.feature) and these is the explanation of some new keywords that are present in the file

The first of them is **Scenario Outline** and it is use to express more concisely examples that use different values in this case the placeholders are within `< >`

The second keyword is **Examples** and it has inside a table the values that are going to be used inside each placeholder

Now that we understand the feature file it's time to face the first step `the secret code is "<code>"`, so lets add this code to the `FeatureContext` file

    public function theSecretCodeIs($secret)
    {
        $this->command = (new CodebreakerCommand())
            ->setSecret($secret);
    }

If we run behat we will find a fatal error becouse `setSecret` method is undefined but that is the expected outcome, we will define it later using phpspec

    bin/behat features/code-breaker_submits_guess.feature