# Gradient-Descent
Understanding Gradient Desent


import pandas as pd

from numpy import * 

#dataset = pd.read_csv("data2.csv", index_col = False)
dataset = pd.read_csv("test_scores.csv", index_col = None)
x = dataset.iloc[:,1]
y = dataset.iloc[:,2]
x + y

starting_b = 0
starting_m = 0
starting_b + starting_m

def compute_error_for_given_dataset(b, m, dataset):
    totalError = 0
    bi = starting_b
    mi = starting_m
    for i in range(0, len(dataset)):
        xi = dataset[i, 1]
        yi = dataset[i, 2]
        totalError += (yi - (m*xi + b))**2 
    return totalError / float(len(dataset))
#compute_error_for_given_points(b, m, points)


       
def step_gradient(b_current, m_current, dataset, learning_rate)
    #gradient descent
    b_gradient = 0
    m_gradient = 0
    N = float(len(dataset))
    for i in range(0, len(dataset)):
        xi = dataset[i, 0]
        yi = dataset[i, 1] 
        b_gradient += -(2/N) * (yi - ((m_current * xi) + b_current))
        m_gradient += -(2/N) * x * (yi - ((m_current * xi) + b_current)) 
    new_b = b_current - (learning_rate * b_gradient)
    new_m = m_current - (learning_rate * m_gradient)
  return [new_b, new_m]
    #step_gradient(b_current, m_current, points, learning_rate)
    
def gradient_descent_runner(dataset, starting_b, starting_m, learning_rate, num_iterations)
    b = starting_b
    m = starting_m
 for i in range(num_iterations):
        b, m = step_gradient(b,m, array(dataset), learning_rate)
  return [b, m]
    
def run():
    #points = genfromtxt('test_scores.csv', delimiter = ',')
    dataset = pd.read_csv('test_scores.csv', delimiter = ',')
    #hyperparameters
    learning_rate = 0.0001
    #y = mx + b
    inittial_b = 0
    initial_m = 0
    num_iterations = 1000
    
    [b, m] = gradient_descent_runner(dataset, inittial_b, initial_m, learning_rate, num_iterations)
    print(b)
    print(m)
    
if _mame_ == '_main_':
    run()
