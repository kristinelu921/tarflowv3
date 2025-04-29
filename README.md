kv cache: storing key and value in autoregressive, so don't have to recompute every time.
- need a separate kv cache for cond and unconditional branches. Otherwise, unconditional queries attend to conditioned kv, which have class info leakage into them.
- Then, difference between uncond + cond shrinks, and we cancel out any learning, creating same affine transform for every patch (converge)

classifier-free guidance: 
- need dropout to train uncondition
- no blending in training
- blending in sampling is necessary so we don't oversharpen and have general baseline

Question: random noise on epoch 38-40, "run w guidance! random noise at 40?", what causes this??

Run of 4's: dulcet-cloud-321

Also want to test permutations:
1. Shifting
2. Random
3. Learned??


