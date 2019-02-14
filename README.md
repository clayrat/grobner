# grobner
A fornalisation of Grobner basis in ssreflect.
It contains one file

``grobner.v``

It defines 

```
Require Import Inverse_Image.
From mathcomp Require Import all_ssreflect all_algebra.
From SsrMultinomials Require Import ssrcomplements poset freeg mpoly.
From matchcomp.contrib.grobner Require Import grobner.

(* p belongs to the ideal generated by L *)

Check ideal.

ideal = 
fun (R : ringType) (n : nat) (L : seq {mpoly R[n]}) (p : {mpoly R[n]})
  =>
  exists t, p = \sum_(i < size L) t`_i * L`_i


(* it is decidable *)

Check idealfP.

idealfP
     : forall (R : fieldType)  (n : nat) (p : {mpoly R[n]})
              (l : seq {mpoly R[n]}),
       reflect (ideal l p) (idealf l p)
```
