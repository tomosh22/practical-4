# CHANGELOG

* v1.1.13 [2019-12-02] Bug fix
    Switch.run_round was not changing the current player correctly after calling Switch.run_player,
    if after adding Switch.direction to i the value of i ends up being outside the bounds
    of Switch.players[] there is no code to remedy this. Added code to change i in edge cases so
    that it loops back to the other end of Switch.players[]
    
* v1.1.12 [2019-11-25] Bug fix and test fix
    Switch.run_player() line 125 was not passing card into Switch.can_discard(), which resulted
    in Switch.cam_discard() returning True every time it was called.
    Also realised that test_run_player__adheres_to_draw2_flag() and
    test_run_player__adheres_to_draw4_flag() didn't actually have to compensate for the
    player discarding after drawing as none of the cards drawn from stock were discardable

* v1.1.11 [2019-11-25] Test fix
    test_run_player__adheres_to_draw2_flag() and test_run_player__adheres_to_draw4_flag()
    weren't compensating for the fact that after a player draws the 2/4 cards, they then
    have to discard one to complete their turn. Also they were asserting that the length
    of the player's hand was 2/4, rather than the difference in length between before their
    turn and after

* v1.1.10 [2019-11-24] Bug fix
    Switch.run_player was not returning True after skipping a player because of skip flag
    and equality operator (==) was being used instead of assignment operator (=) to change
    flags back to False

* v1.1.9 [2019-11-24] Bug fix
    When Switch.get_normalized_hand_sizes() attempts to rotate sizes it doesn't do anything.
    Flipped around sizes[idx:] and sizes[:idx] so sizes is rotated properly

* v1.1.8 [2019-11-24] Bug fix
    Switch.discard_card() multiplies Switch.direction by 1 when it tries to change
    direction after discarding a king, which doesnt do anything. Changed to multiplying by -1
    
* v1.1.7 [2019-11-24] Bug fix
    Switch.discard_card() sets draw2 to True when a 4 is played instead of when
    2 is played, changed to 2
    
* v1.1.6 [2019-11-24] Test fix
    test_can_discard_allows_ace() attempts to play a king not an ace, changed
    this to an ace instead
    
* v1.1.5 [2019-11-24] Bug fix
    Switch.can_discard() line 185 states that both the suit and value must
    match, instead of just one of them. Changed and to or
    
* v1.1.4 [2019-11-24] Bug fix
    cards.py line 6 there are 2 aces generated for each suit
    so removed one of them
    
* v1.1.3 [2019-11-24] Bug fix
    Switch.pick_up_card() range(1,n) on line 159 doesn't compensate
    for the fact that range() doesnt include the last number so
    changed to range(1,n+1)
    
* v1.1.2 [2019-11-24] Bug fix
    Added instantiation of switch object to make the game start
    
* v1.1.1 [2019-11-24] Bug fix
    Added missing closing bracket in players.py:50
    
* v1.1.0 [2019-11-08]: Added a SmartAI computer opponent.
  Added strategy players.SmartAI
  None of the bugs have been fixed.

* v1.1.0 [2019-10-25]: First major release.
  This version is known to contain some bugs.