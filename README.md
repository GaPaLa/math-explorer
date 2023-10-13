# adversarial proof exploration

If we want a proof generator, we will want to propose increasingly difficult proofs.

To do this, we could make two networks which are adversaries - one which is given a conjecture to find a proof for/against, and another which generates conjectures.

To minimize compute, it will be useful to ensure all statements are valid and instead of letting the model generate it free-form i.e. next token prediciton, we will give it a list of valid actions it could take i.e. axioms it could apply to transform the current statment.

Both networks then work by applying sequences of valid axioms to a given statement to either (in the case of the solver) reach a proof, or (in the case of the adversary) a state which is sufficiently hard for teh solver to reach - a conjecture

It would probably be beneficial (i.e. lower resource and faster learning learning i.e. similar to upside down reinforcement learning) to use the same network as both problem poser and proof generator.
Could probably just provide a flag token to get it to switch between the two.
