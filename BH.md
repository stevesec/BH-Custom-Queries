1. Computers that do not have LAPS: 

``MATCH (c:Computer {haslaps:false,enabled:TRUE}) WHERE toupper(c.operatingsystem) CONTAINS 'WINDOWS' RETURN c.name,c.operatingsystem``

3. Unsupported Operating Systems: 

```MATCH (c:Computer {enabled: true})
WHERE toLower(c.operatingsystem) CONTAINS toLower('2000') OR
      toLower(c.operatingsystem) CONTAINS toLower('2003') OR
      toLower(c.operatingsystem) CONTAINS toLower('2008') OR
      toLower(c.operatingsystem) CONTAINS toLower('xp') OR
      toLower(c.operatingsystem) CONTAINS toLower('vista') OR
      toLower(c.operatingsystem) CONTAINS toLower('7') OR
      toLower(c.operatingsystem) CONTAINS toLower('me')
  AND NOT toLower(c.operatingsystem) CONTAINS toLower('2012') AND
      NOT toLower(c.operatingsystem) CONTAINS toLower('2016') AND
      NOT toLower(c.operatingsystem) CONTAINS toLower('2022') AND
      NOT toLower(c.operatingsystem) CONTAINS toLower('10') AND
      NOT toLower(c.operatingsystem) CONTAINS toLower('11')
RETURN c.name, c.operatingsystem
