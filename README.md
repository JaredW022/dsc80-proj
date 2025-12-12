# League of Legends Analysis: Wards vs. Dragons

Step 1:
League of Legends is a five‑versus‑five strategy game in which two teams battle to destroy the opposing team’s base. At the professional level, teams don’t just rely on raw mechanical skill – they win by controlling information and neutral objectives. The most prestigious tournament in this competitive ecosystem is the annual World Championship (Worlds), where top teams from regions around the world compete for the world title in a multi‑week event watched by millions.
One of the most important neutral objectives in League of Legends is the dragon. Throughout the game, teams can “secure” dragons by killing them, which grants powerful permanent buffs such as bonus movement speed, increased attack damage/ability power, or shorter cooldowns on abilities. Stacking several dragons – or securing the powerful “Dragon Soul” – can dramatically shift the outcome of a game. Because of this, professional teams devote a lot of resources to contesting dragons.
Another critical but less visible resource is vision. Teams place “wards” on the map to reveal fog‑of‑war and track the positions of enemies and neutral objectives. Good vision lets teams safely set up for dragons, catch opponents out of position, and avoid being ambushed. Intuitively, we might expect teams that invest more in vision around the map to do a better job of controlling dragons – but how strong is that relationship in actual professional games?
In this project, we use a dataset compiled by a community resource that aggregates detailed statistics from professional League of Legends matches. Our subset focuses on games played at the World Championship over several years. Each row in our cleaned DataFrame corresponds to a single team in a single game at Worlds, meaning that every game appears twice (once for each team). In total, our cleaned dataset contains [N] rows and [M] columns.

For the rest of this project, we focus on a few key columns that are most relevant to our question:
dragons: the number of elemental dragons a team secured in that game.

wards_placed (or your column name): the total number of wards that team placed.

wards_per_minute: a derived feature equal to wards_placed divided by game length in minutes, which measures how actively a team uses vision over time.

gameid: a unique identifier for each match, used to group the two teams in the same game.

team: the name or identifier of the team.

result (or win): whether the team won or lost the game

wcpm: the number of enemy wards the team destroyed, divided by game length. This captures how effectively the team denies the enemy’s vision. 
controlwardsbought: the total number of control wards the team purchased. Control wards are special wards that reveal and disable enemy wards, so higher values indicate a stronger focus on long-term, persistent vision. 

wcpm: the number of enemy wards the team destroyed, divided by game length. This captures how effectively the team denies the enemy’s vision. 
visionscore: riot’s composite vision metric that rewards placing useful wards, clearing enemy wards, and providing vision of unseen enemies and objectives. A higher vision score reflects better overall vision control, not just raw ward counts. 

totalgold: the total amount of gold the team earned during the game, across all sources (minions, monsters, objectives, kills, etc.) This is a proxy for overall economic strength and can help separate the effect of vision from simply “being ahead.”

Our central research question is:
How strongly is a team’s vision control – measured by the number of wards they place (and wards per minute) – associated with the number of dragons they secure in a Worlds game?

This question matters both to players and to analysts. If we find a strong relationship, it would support the idea that investing in vision is a key part of objective control strategy at the highest level of play. On the other hand, if the relationship is weak, it could suggest that other factors (like early‑game lane pressure, jungle pathing, or team‑fight execution) are more important than raw ward count when it comes to securing dragons. Throughout the rest of this project, we’ll explore this relationship through exploratory data analysis, hypothesis testing, evaluating missingness, and predictive modeling.
