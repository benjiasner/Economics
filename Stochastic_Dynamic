#Benji Asner's Markov Chain code

import numpy as np

# conditional probabilities regarding employment, must be values between zero and 1:
p = .3 # probability that unemployed workers remain unemployed
q = .8 # probability that employed workers remain employed
#initial unemployment fractions:
initUn = .2
initEm = 1 - initUn
#create initial em/unemployed fraction vector
init_vector_row = np.array([initUn, initEm])
#create the transition matrix
TransMatrix = ([p, 1-p], [1-q, q])
#we set the number of iterations to be done, n, e.g. the exponent TransMatrix^n
#the iterations are taken care of by the np.linalg.matrix_power function
n = 400
Mresult = np.linalg.matrix_power(TransMatrix, n)

mu = np.dot(init_vector_row, Mresult)
#uncomment the below to see the values of the n-iterated transition matrix and corresponding mu
#print("Transition Matrix multiplied " + str(n) + " times:")
#print(Mresult)
#print("Mu with " + str(n) + "th power iterated Transition Matrix:")
#print(mu)

m = n + 1
Mresult2 = np.linalg.matrix_power(TransMatrix, m)
mu2 = np.dot(init_vector_row, Mresult2)
#uncomment the below to see the values of the m-iterated transition matrix and corresponding mu
#print("Transition Matrix multiplied " + str(m) + " times:")
#print(Mresult2)
#print("Mu with " + str(m) + "th power iterated Transition Matrix:")
#print(mu2)

#Now we can explicitly check whether we've converged by seeing if the values of successive mu's are equal

if mu[0] == mu2[0] and mu[1] == mu2[1]:
    print("We have convergence and thus Mu-star, due to the fact that the "
            + str(n)+ "th iteration equals the " + str(m)+ "th iteration!")
    print("Given p="+str(p)+" and q="+str(q)+", the value of Mu-star is: "+str(mu))
    print("and the corresponding Transition Matrix is: ")
    print(Mresult)
else:
    print("You would be well served to increase the value of n, as your different (non-concatated) mu values do not match:")
    print( str(mu[0]) + " does not equal " + str(mu2[0]) + " (look closly at the tails of the decimals!)")
    print( str(mu[1]) + " does not equal " + str(mu2[1]) + " (look closly at the tails of the decimals!)")
