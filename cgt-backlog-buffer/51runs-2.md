## Session 51 machine runs — batch 2a (Janson + Poisson + thresholds)

```
B1 K_6: edge-sharing triangle pairs=90 formula 6*C(n,4)=90 match=true
B1 K_7: edge-sharing triangle pairs=210 formula 6*C(n,4)=210 match=true
B1b G(100,1/2): mu=20212.5 Delta=735229.6875 Delta/2=367614.84375 jansonI-bound=exp(347402.34375)=Infinity (vacuous: bound>1)
B1c G(n,1/n) n=100: mu=0.161700 (1/6=0.166667) Delta=2.3527e-3 jansonI=exp(-0.16052363250000004)=0.851698 truth-e^(-1/6)=0.846482
B1c G(n,1/n) n=1000: mu=0.166167 (1/6=0.166667) Delta=2.4850e-4 jansonI=exp(-0.16604274862575)=0.847010 truth-e^(-1/6)=0.846482
B1c G(n,1/n) n=10000: mu=0.166617 (1/6=0.166667) Delta=2.4985e-5 jansonI=exp(-0.1666041774986251)=0.846535 truth-e^(-1/6)=0.846482
B2 n=60 c=0.5: tri-free=253/300=0.843 poisson-est=0.979 mean-count=0.260 poisson-mean=0.021
B2 n=60 c=1: tri-free=125/300=0.417 poisson-est=0.846 mean-count=1.637 poisson-mean=0.167
B2 n=60 c=2: tri-free=3/300=0.010 poisson-est=0.264 mean-count=10.347 poisson-mean=1.333
B2 n=120 c=0.5: tri-free=258/300=0.860 poisson-est=0.979 mean-count=0.267 poisson-mean=0.021
B2 n=120 c=1: tri-free=141/300=0.470 poisson-est=0.846 mean-count=1.487 poisson-mean=0.167
B3 n=120 c=1 histogram (0..5,6+): 0:141 1:28 2:67 3:21 4:21 5:8 6+:14; TV-dist vs Poisson(1/6)=0.8218
B2 n=120 c=2: tri-free=4/300=0.013 poisson-est=0.264 mean-count=10.267 poisson-mean=1.333
B4 m(H): K3=1 K4=1.5 C4=1 K4-e=1.25 K5=2 paw=1
B4b n=60 lambda=0.6: P(K4)=118/200=0.590 poisson-est(1-e^(-lam^6/24))=0.002
B4b n=60 lambda=1: P(K4)=193/200=0.965 poisson-est(1-e^(-lam^6/24))=0.041
B4b n=60 lambda=1.6: P(K4)=200/200=1.000 poisson-est(1-e^(-lam^6/24))=0.503
B4b n=60 lambda=2.5: P(K4)=200/200=1.000 poisson-est(1-e^(-lam^6/24))=1.000
```
