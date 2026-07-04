1. Smart Contract (Intelligent Contract)
contracts/voting_contract.py

class VotingContract:
    def __init__(self):
        self.proposals = {}
        self.votes = {}

    def create_proposal(self, proposal_id: str, description: str):
        self.proposals[proposal_id] = {
            "description": description,
            "yes": 0,
            "no": 0
        }
        return f"Proposal {proposal_id} created"

    def vote(self, proposal_id: str, vote: str):
        if proposal_id not in self.proposals:
            return "Proposal not found"

        if vote == "yes":
            self.proposals[proposal_id]["yes"] += 1
        elif vote == "no":
            self.proposals[proposal_id]["no"] += 1

        return self.proposals[proposal_id]

    def get_result(self, proposal_id: str):
        return self.proposals.get(proposal_id, "Not found")



		
