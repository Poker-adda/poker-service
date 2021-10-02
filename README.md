# poker-service

Raw Logic
while(!game.IsConcluded())
        {
        hand hand = game.initiateHand(); // In this method call hand.blinds()
        
        // Pre-flop Betting round
        hand.beginPreFlopBettingRound(); // -> In this method distribute cards
        Player player = hand.utg();
        while(!hand.IsConcluded() || !hand.IsPreFlopConcluded() )
        {
            player.play(Move move, BettingValue value);
            player = hand.nextPlayer();
        }

        // Flop Betting ound
        hand.BeginFlopBettingRound();
        Player player = hand.sb();
        while (!hand.IsConcluded() || !hand.IsFlopConcluded())
        {
            player.play(Move move, BettingValue value);
            player = hand.nextPlayer();
        }

        // Turn Betting Round
        hand.BeginTurnBettingRound();
        Player player = hand.sb();
        while (!hand.IsConcluded() || !hand.IsTurnConcluded())
        {
            player.play(Move move, BettingValue value);
            player = hand.nextPlayer();
        }

        // River Betting Round
        hand.BeginRiverBettingRound();
        Player player = hand.sb();
        while (!hand.IsConcluded() || !hand.IsRiverConcluded()) // conclusion at river concludes concludes Hand
        {
            player.play(Move move, BettingValue value);
            player = hand.nextPlayer();
        }
    }
