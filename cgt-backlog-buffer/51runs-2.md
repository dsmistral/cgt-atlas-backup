## Session 51 machine runs — batch 2a v2 (Janson + Poisson + thresholds; 32-bit-word fix; supersedes the defective v1)

```
B1 K_6: edge-sharing triangle pairs=90 = 6*C(6,4) [verified] | K_7: 210 = 6*C(7,4) [verified]
B1b G(100,1/2): mu=20212.5 Delta=735229.6875 Delta/2=367614.84375 jansonI bound>1 VACUOUS [verified]
B1c G(n,1/n) n=100: mu=0.161700 Delta=2.3527e-3 jansonI=0.851698 truth=0.846482 [verified]
B1c G(n,1/n) n=1000: mu=0.166167 Delta=2.4850e-4 jansonI=0.847010 truth=0.846482 [verified]
B1c G(n,1/n) n=10000: mu=0.166617 Delta=2.4985e-5 jansonI=0.846535 truth=0.846482 [verified]
B4 m(H): K3=1 K4=1.5 C4=1 K4-e=1.25 K5=2 paw=1 [verified]
B2 n=60 c=0.5: tri-free=296/300=0.987 poisson-est=0.979 mean-count=0.013 poisson-mean=0.021 mean-edges=14.5 expected-edges=14.8 CH4-GATE(0.98)=PASS
B2 n=60 c=1: tri-free=250/300=0.833 poisson-est=0.846 mean-count=0.173 poisson-mean=0.167 mean-edges=29.4 expected-edges=29.5 CH4-GATE(0.855)=PASS
B2 n=60 c=2: tri-free=91/300=0.303 poisson-est=0.264 mean-count=1.240 poisson-mean=1.333 mean-edges=59.4 expected-edges=59.0 CH4-GATE(0.26)=PASS
B2 n=120 c=0.5: tri-free=294/300=0.980 poisson-est=0.979 mean-count=0.020 poisson-mean=0.021 mean-edges=29.3 expected-edges=29.8 CH4-GATE(0.975)=PASS
B2 n=120 c=1: tri-free=249/300=0.830 poisson-est=0.846 mean-count=0.193 poisson-mean=0.167 mean-edges=59.9 expected-edges=59.5 CH4-GATE(0.89)=PASS
B2 n=120 c=2: tri-free=95/300=0.317 poisson-est=0.264 mean-count=1.340 poisson-mean=1.333 mean-edges=119.3 expected-edges=119.0 CH4-GATE(0.27)=PASS
B3 n=120 c=1 histogram (0..5,6+): 0:249 1:45 2:5 3:1 4:0 5:0 6+:0; TV-dist vs Poisson(1/6)=0.0330
B4b n=60 lambda=0.6: P(K4)=0/200=0.000 mean-edges=69.3 expected-edges=70.5
B4b n=60 lambda=1: P(K4)=6/200=0.030 mean-edges=114.2 expected-edges=117.4
B4b n=60 lambda=1.6: P(K4)=82/200=0.410 mean-edges=184.3 expected-edges=187.9
B4b n=60 lambda=2.5: P(K4)=200/200=1.000 mean-edges=289.1 expected-edges=293.6
CH4-GATE: ALL PASS (fresh sampler consistent with the Ch. 4 lab Part 2 recorded outputs)
```
