Compound Poisson Process Simulation (S(t))

This repository contains a simple, interactive Shiny application written in R (app.R) that simulates a Compound Poisson Process with Exponentially distributed jump sizes.

The purpose of this simulation is to visualize the process over time (Sample Path) and compare the simulated distribution of $S(t)$ at a specific time $t_0$ against its theoretical mean and variance.

1. Mathematical Model

The process $S(t)$ is defined as the total accumulated size of events up to time $t$:

$$S(t) = \sum_{i=1}^{N(t)} X_i$$

Where:

$N(t)$ is a Poisson Process with arrival rate $\lambda$. (The interarrival times are $\text{Exp}(\lambda)$.)

$X_i$ is the size of the $i$-th jump, where $X_i \sim \text{Exp}(\beta)$ (Exponentially distributed with rate $\beta$).

Theoretical Properties

The theoretical mean and variance of $S(t)$ are calculated as follows (see DERIVATION.md for the full derivation):

Statistic

Formula

Mean

$E[S(t)] = \frac{\lambda t}{\beta}$

Variance

$Var[S(t)] = \frac{2 \lambda t}{\beta^2}$

2. Contents

app.R: The core R script containing the Shiny UI and Server logic.

README.md: This file.

DERIVATION.md: A detailed document showing the mathematical derivation of the $S(t)$ distribution.

How to Run the App (Locally)

Save the app.R file locally.

Ensure you have the shiny package installed in R (install.packages("shiny")).

Run the application from your R console:

# Ensure app.R is in your current working directory
shiny::runApp("app.R")


3. App Functionality

The application features two main tabs:

Sample Path: Plots a single realization of $S(t)$ over the time horizon $T_{\text{max}}$.

Distribution at $t_0$: Generates a large number of independent $S(t_0)$ values (Monte Carlo simulation) and displays the resulting histogram, comparing the empirical results to the known theoretical mean and variance.
