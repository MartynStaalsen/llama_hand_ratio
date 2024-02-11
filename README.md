# llama_hand_ratio
Python code to answer a question about the "Don't L.L.A.M.A" card game

## Context

The card came "Don't L.L.A.M.A" is essentially uno with extra rules. 
This game is played with a deck of cards containing 8 instances of the following 7 cards: [1, 2, 3, 4, 5, 6, "Llama"]. The game involves playing cards from your hand onto a discard, with the constraint that you must either match the current discard or increment it by 1. The "Llama" card acts as an Ace might in traditional 52 card games, in that it can be played on a 6 and causes wrap-around back to 1. Players take turns discarding a single card, choosing either to match the current discard or play the next in the sequence. Players who cannot discard legally must draw an additional card. Players may also choose to "fold" -- ceasing to participate in the remainder of a round and accepting a penalty points for the cards remaining in their hand. Play continues until all players have folded, or one player discards their entire hand (a feat rewarded by a point bonus).

In some rounds, a single player may find themselves the only one yet to fold. In this situation, that player may continue to discard cards as long as they can, but cannot draw any new cards. If this last remaining player has a consecutive sequence of cards, they are able to play out all their cards and attain the point bonus. If their hand forms such a consecutive sequence, I term this a "llamable" hand. A llamable hand is one which can be arranged to form a consecutive "run", ignoring duplicates and respecting wrap-around. 

After playing this game one evening, I was curious about the probability of being dealt a "llamable" hand. Obviously, this probability is not highly relevant to real gameplay, since:
- one will indubitably discard some cards before being the last player standing
- the ability to actully "play out" with a llamable hand is constrained by the current discard inherited by the last player standing

However, I still thought it'd be fun and relativly simple to calculate. After a quick stab at the problem, I realized that a full treatment of edge cases and proper handling of wrap-around in sequence detection would make the problem yet more intereseting.

