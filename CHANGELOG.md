# CHANGELOG

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