# laboratorioN3
turtles-own[energia edad muertesubita x]
to configuracion 
clear-all
create-turtles 20 
  [
  setxy random-xcor random-ycor 
set energia 10
set edad 0
set muertesubita false
  ]
  ask patches [ set pcolor green]
end
to programa 
mover
comer
muerte
end

to mover
  ask turtles [
  set heading heading + random 20
    forward 1
  set edad edad + random  4
  set energia energia - 1
     
  ]
end
to comer
  ask turtles [
    if(pcolor = green)[
    set energia energia + random 3
    set pcolor black
    ]
  ]
end
to muerte
  ask turtles[
  if energia < 0 
    [die]
  if edad > 120
    [die]  
  set x random 10
    if (x = 7) 
      [
    set muertesubita true
        if (muertesubita = true)[die]   
    ]
    
    ]
end
