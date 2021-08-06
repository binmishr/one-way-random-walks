# one-way-random-walks

A rather puzzling riddle from The Riddler on an 3×3 directed grid and the probability to get from the North-West to the South-East nodes following the arrows. Puzzling because while the solution could be reasonably computed with an R code like

sucz=0
for(i in 1:2^12){
  path=intToBits(i)[1:12]
  sol=0
  for(j in 1:12)sol=max(sol,
        prod(path[paz[[j]][paz[[j]]>0]]==01)*
        prod(path[-paz[[j]][paz[[j]]<0]]==00))
  sucz=sucz+sol

where paz is the list of the 12 possible paths from North-West to South-East (excluding loops!), leading to a probability of 1135/2¹², I could not find a logical reasoning to reach this number. The paths of length 4, 6, 8 are valid in 2⁸, 2⁶, 2⁴ of the cases, respectively and logically!, but this does not help as they are dependent.
