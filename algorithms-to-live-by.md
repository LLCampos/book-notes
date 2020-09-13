# Chapter 1 - Optimal Stopping

When to stop searching and pick e.g. an apartment, a life partner, a job, etc, in order to increase your chances of picking the best candidate?

## Secretary Problem
* You can only know the "ordinal quality" of the candidate
* If you don't make an offer to the candidate the moment you evaluate it, you will not be able to make an offer later
* Offers are always accepted
* You know the number of candidates you can evaluate
* You evaluate the candidates at random, one at a time

**Solution:** Look-The-Leap Rule: Evaluate 37% of the candidates; after that, make an offer to the first one better than the best of the previous 37%.

**Quality of Solution:** This will lead to picking the best 37% of the time.

The algorithm also works when you don't have a limited *number* of candidates, but a limited amount of *time* to search for candidates. In this case, spend 37% of the time just evaluating candidates and not making an offer to anyone.

## Secretary Problem with Rejection
* Same as Secretary Problem but candidates can reject you!

**Solution:** If you have 50% chance of rejection, follow the Look-The-Leap Rule but start making offers after only 25% of the candidates were evaluated.

**Quality of Solution:** This will lead to picking the best 25% of the time.

## Secretary Problem with Recall
* Same as Secretary Problem, but you can go back and making an offer to an candidate you passed before

**Solution:** If an immediate proposal is a sure thing but belated proposals are rejected half of the time, look at 61% without making offers. After that, make an offer to the first one better than what you've already evaluated. If after you evaluated everyone, you were not able to pick anyone (or were rejected when you tried), make an offer to the best you've seen, from better to worst, until someone accepts.

**Quality of Solution:** This will lead to picking the best 61% of the time.

## Secretary Problem with Cardinal Quality
* Same as Secretary Problem but we know the Cardinal Quality of the candidates

**Solution:** Assumes normal distribution of candidates quality. Use *Threshold Rule*: pick the first candidate that it's above a certain threshold. This threshold depends on the number of candidates/time left. If number of candidates is big, threshold should be high. If you have less candidates to choose from, you should lower the threshold.

**Quality of Solution:** If you do this in a mathematically correct way, you'll pick the best candidate 58% of the time.

## When to Sell
* When receiving an offer (e.g. for a house or a job offer) we have to decide if to accept of reject
* Rejecting has costs: more time waiting and we're not sure of next offer will be better
* The goal, then, is not to try to accept the best possible offer, but obtain the most value through the whole process. We're trying to maximize (value_of_offer - cost)

* Assuming that:
    a) Offers will not run out
    b) We have unlimited time to receive offers
    c) We know the range of possible offers we will receive

* The above assumptions apply when, for example, you're looking for a job but are currently employed. Re a), there are a huge number companies that can make you offers. Re b), you're not going to run out of money, since you already have a job! Re c) there are ways to know the range of possible salaries for your skill levels

* The decision depends only on the cost of rejection and on max and min offers you expect to receive

* "(...) if waiting costs half or more of our expected range of offers (...) then there's no advantage whatsover to holding out (...)"

* Heuristic: if cost of waiting is too high, just accept the first offer you receive.

* If cost is really low, it's probably best to wait for an offer close to the max of the range of offers you expect to receive

* I think I kind of intuitively did this on my first job hunt. My family economically supporting me lead to the costs of rejecting offers to be lower than otherwise, which lead to me to accept a better offer than I would otherwise.

* I don't think this idea is new: economic safety leads to one only accepting good offers. On the other hand, people with less economic safety will accept bad offers, not improving their finances. The rich get richer and the poor get poorer.

## When to Park

* Goal is to minimize a) Time looking for a spot and b) Distance from the spot to final destination.

**Solution:** Look-Then-Leap Rule. "The optimal stopping driver should pass up all vacant spots occurrence more than a certain distance from the destination and then take the first space that appears thereafter". The "certain distance" only depends on the occupancy rate. There's table on the book showing these distances for a bunch of occupancy rates.

# Chapter 2 - Explore/Exploit

* "(...) the internal makes the strategy" - When you have a lot of time, exploration has a lot of value. When time is limited, it's time to exploit.

## Multi-armed bandit problem with geometrically discounted payoffs

**Solution:** Always play the arm with the highest Gittins index

"(...) something you have no experience whatsoever is more attractive than a machine that you know pays out 70% of the time!"

"Exploration in itself has value, since trying new things increases our chances of finding the best."

* Assumes no cost of changing arms. If there are costs, the algorithm is no longer optimal

* The Gittins index is hard to calculate on the fly
