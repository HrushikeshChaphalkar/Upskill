**Question:**

Find players who participated in the Olympics representing more than one team. To detect multiple teams please inspect team column and how are multiple teams structured.
Output the player name, team, games, sport, and the medal.

-------------------------------------------------------------------
**Solution:**
```python
output_cols = ['name', 'team', 'games', 'sport',  'medal']
result = (
    olympics_athletes_events[olympics_athletes_events["team"].str.contains("/")]
    [output_cols]
)
```