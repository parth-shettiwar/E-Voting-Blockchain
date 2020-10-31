# E-Voting using Blockchain
Microsoft codefundoo 2019
### Basic idea
Our e-voting project follows the following rules 
1. The vote given by a person cannot be seen by any other person.
1. People living in all region having an internet connection can vote.
1. Only eligible people can vote and that also only once.
1. The proposals of the candidates remain the same throughout the election.
1. The election results are displayed just after the end of elections.

### Implementation
#### People
* **Admin** Is responsible for the creating of elections, starting of elections and the ending of elections. Also he/she enrolls the name of people in the voter lists and also the announcing of the result.
* **Voters** They cast their votes by going at their respective constituencies. They are given the wallet pin and ID by their respective local people.
* **Regional nodes**  They will represent a region(for example a district) from where a set of candidates can vote. When the election is created, they would interact with their smart contract. Whenever a candidate votes from a region using the smart contract, its verified by all other regional nodes. 
#### Process
* **Election Creation** Using a dApp ,the admin makes an election creation master smart contract which will have list of all candidates and voting regions.
* **Regional nodes creation** The master smart contract will create set of ballot smart contracts where each will have a list of all voters eligible to vote from that region. The regional node will get permssion to interact with his corresponding smart contract,
* **Voter Registration** While creating a list of eligible candidates, the admin has to securely authenticate and authorize them.The voter will get an elctronic ID after getting eligible. Also a wallet will be generated for each voter.
* **Vote Transaction** The voter will interact with the smart contract of his region. The vote is appended to the blockchain if consensus is reached with majority of regional nodes.This will generate a transaction ID.Once the vote is casted, the wallet will reduce to 0, ensuring no double voting by a voter.
* **Tally Result** This is done by each smart contract of a region on the fly.When election is over, the final result for each region is published. 
* **Vote Verification** The voter, who had received a transaction ID, can verify his vote with the admin after showing his electronic ID.The admin using a blockchain explorer with locate the transaction and voter can see his vote.

**We will be using Geth framework for the hackathon as it is user friendly and has high transaction rate.**

### Scope of improvement
1. A single ballet contract is a single point of failure. If this breaks in the middle of the voting process, then there goes the election(that constituency).
1. Different types of elections can be conducted like open elections or private elections from the same app (*like Netvote*).
1. There is some type of centralization in this process (the admin). We would want to have completely decentralized elections.
