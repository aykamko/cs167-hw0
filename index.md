---
layout: default
---

# About Me

My name is [Aleks Kamko](http://alekskamko.com). I'm a fourth year undergraduate in the EECS major. Ever since taking Operating Systems at Cal, I have been fascinated with system architecture--consequently, I am a TA for Operating Systems for 2 semesters now. This has been a large motivation for me taking this course: I am very interested in the architecture designs and programming paradigms underlying the various flavors of parallel computing. I am also interested in Data Science, so I hope this class will augment my repertoire of techniques to write efficient, parallel data analysis algorithms and systems. And of course, parallel computing is becoming more and more important in industry; I believe that knowing how to properly write and use parallel programs is an invaluable skill -- and it's pretty cool one too!

# Parallel Computing in Medical Imaging

In the past decade, Medical Imaging has emerged as one of the most important applications of parallel computing. In particular, GPU processing has accelerated MRI reconstruction algorithms by a factor of 21x compared to conventional quad-core CPUs, and has reduced image error along the way [[1]](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3142623/).

In the past, MRI scan patterns and reconstruction applications were specifically designed for CPUs. Scans would be done in a Cartesian trajectory, allowing for CPUs to easy reconstruct the images using FFT. However, MRIs can benefit significantly by using more advanced image reconstruction techniques. MRIs tend to produce better images (less noise, fewer artifacts, etc.) if scans are done in radial or spiral trajectories [see image below], but this leads to much more expensive reconstruction algorithms, which are computationally expensive for CPUs.

![](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3142623/bin/nihms72580f3.jpg)

With the advent of GPGPUs, some of these advanced imaging techniques have become feasible. For example, GPUs can "incorporate anatomical information to reduce noise while preserving the resolution of known image features". This method, known as Anatomically Constrainted Reconstruction, produces high resolution, low-noise MRI images [2], much more useful than previous FFT-based reconstructions. In the Stone et al. paper, the research team was able to use this advanced technique to reduce image error from 42% with the CPU FFT technique to just 13%, and in just 49 seconds! For comparison, the CPU took 22.5 minutes to execute the same computation.

![](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3142623/bin/nihms72580f4.jpg)

The application was targeted for a NVIDIA Quadro FX 5600 graphics card from 2008, and the team used NVIDIA's CUDA library in ANSI C to code the parallel anatomically constrained reconstruction program.

These remarkable results are just one example of the application of parallel computing to Medical Imaging -- parallel computing and GPUs have also made tremendous improvements in CT scans and fMRIs as well [[3]](http://blogs.nvidia.com/blog/2010/04/21/the-world-is-parallel-gpus-speed-medical-imaging/).

----

[[1]](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3142623/) Stone, S.S. et al. “Accelerating Advanced MRI Reconstructions on GPUs.” Journal of parallel and distributed computing 68.10 (2008): 1307–1318. PMC. Web. 29 Jan. 2016.

[2] Haldar J, Hernando D, Song S-K, Liang Z. Anatomically constrained reconstruction from noisy data. Magnetic Resonance in Medicine. 2008;59:810–818.

[[3]](http://blogs.nvidia.com/blog/2010/04/21/the-world-is-parallel-gpus-speed-medical-imaging/) http://blogs.nvidia.com/blog/2010/04/21/the-world-is-parallel-gpus-speed-medical-imaging/
