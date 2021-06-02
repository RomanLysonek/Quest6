# Quest6
Repo for Quest6 queries

1)
select team.name, count(*) as nb_student
     from player
     join wizard on
     wizard.id=player.wizard_id
     join team on
     team.id=player.team_id
     group by team_id
     order by nb_student desc;
2)
select team.name
     from player
     join wizard on
     wizard.id=player.wizard_id
     join team on
     team.id=player.team_id
     group by team_id
     having count(*)>=14;
3)
select wizard.firstname, wizard.lastname, player.enrollment_date
     from player
     join wizard on
     wizard.id=player.wizard_id
     join team on
     team.id=player.team_id
     where team.name='Gryffindor'
     having dayofweek(player.enrollment_date)=2
     order by player.enrollment_date;
