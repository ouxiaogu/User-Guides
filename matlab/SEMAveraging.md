Hibino, Daisuke, et al. "High-accuracy OPC-modeling by using advanced CD-SEM based contours in the next-generation lithography." SPIE Advanced Lithography. International Society for Optics and Photonics, 2010.

### current issues for iCal

1. extract high quality SEM-contours using the same algorithm as the CD-measurement.
2. the problem of unequal SEM edge quality between vertical and horizontal edge
3. develop a contour alignment / averaging technology to complex asymmetric 2D structures

**advanced Measurement Based Averaged Contour** (MBAC) 
**Fine SEM Edge** (FSE)
**Measurement Based Contour** (MBC)

1. using normal SEM images and without any alignment
2. the case with normal SEM image and first alignment and averaging,
3. the case using normal SEM images and advanced alignment and averaging
4. the case with advanced alignment and averaging and FSE images.


### Alignment technology: Between Mask polygon and SEM Contour 

1. symmetric structures

    like Line and Space Pitch, Contact-hole and End of Line (EOL).

    By **center-of-gravity of each pattern**

2. complex and asymmetric
    
    **MBAC**

    1. Image acquisition
    2. two step edge detection, 
        1. image based edge detection ## This is the common image based algo like, Sobel, Robert, Canny
        2. measurement based edge detection, ## This may correspond to the our gauge CD & SEM contour bias, iCal have *C-Displacement* and *SEMContourOffset* 
    3. MBC (Measurement Based Contour) advanced alignment ## ?
        1. 1st alignment, to eliminate the X-Y shift and Rotation caused by CD-SEM ## means the SEM movement form die to die? 
            
            only adjust three parameters, delta_x, delta_y, delta_theta to minimize the cost:
            "\delta distance = |(P_{MASK} + A - P_{SEM})*G_i|"

        2. 2nd alignment, between 1st aligned MBC and a simulated-contour:

            1. the 1st aligned MBC to overlay with a simulated-contour ## this is what our 
            
                to mini the sampling point distances between 1st aligned MBC and the simulated-contour. **S**: simulation points, **M**: 1st aligned MBC contour

                "distance_i = sqrt((Sx - Mx)**2 + (Sy - My)**2) "
                "Contour_RMS = sqrt(sum( distance_i) /N)"


    4. Advanced aligned MBC averaging, ?
    5. GDS creation from Advanced MBAC, ?


### Averaging technology: Between SEM image Die 1 & Die 2

1. symmetric structures

    - By **center-of-gravity of each pattern**, R & T
    - By edge of the shape, T 
    - advanced By **center-of-gravity of each pattern**, R & T & shear 

2. Asymmetric structures

    iteration simplex: to minimize the EPE error



## The challenge of the iCal jobs

Granik, Yuri, and Ir Kusnadi. "Challenges of OPC model calibration from SEM contours." SPIE Advanced Lithography. International Society for Optics and Photonics, 2008.

challenges:

    1. process inevitable gaps
    2. discontinuities
    3. roughness of the SEM contours

### 1. the limitation of CD-based model:

1. deficient in represent 2D effects, CR, isoLE, 
2. difficulty in delivering measurement to describe bridging, pinching and un-printing

### 2. the benefits in contour-based calibration:

1. it accommodates asymmetrical CD,
2. it captures missing information like bridging, pinching, missing-print, isolated line-end pullback, 
3. it handles corner rounding and other 2D effects
4. it involves massive measurement data since single SEM picture may contain hundreds or thousands contour points.

### 3. the cost function of iCal

1. if both Measurement contour and simulated contour are continuous, use XOR to compute the different areas.
2. if 1 or more contour is discontinuous, then compute their Hausdorff distance.
    - (1) Iterate points in contour A, find nearest point in contour B, memorize max distance Ma (one-sided distance), 
    - (2) Iterate points in B, find nearest point in A, memorize max distance Mb (another one-sided distance),
    - (3) Hausdorff distance is max(Mb, Ma).
3. represent the measurement contour by a set of points and the simulation contour by a set of edges. The distance is calculated as follow: 

    (1) For each point of measurement contour, find the nearest point on the simulation contour, 
    (2) Reciprocally, for each edge of the simulation contour, find the nearest point on the measurement contour, 
    (3) Calculate RMS (not a maximum like in the Hausdorff distance) of all deviations.

    **Methods to compute distance**

    (1) *Vector Enumeration*:
        
        M2E: time, O(|M|*|E|)
        E2M: time, O(|E|)
        Storage: O(|M|+|E|)

    (2) *Dense Distance Map*:

        M2E: time,

        - given a simulated contour edges set, create a dense array, every position of the array store the distance from this position to the nearest edge.
        - given a measurement contour points set, create a dense array, every position of the array store the distance from this position to the nearest measurement contour point.


### 4. the challenges of  iCal

1. The need to minimize alignment issues, i.e. shift, scaling, or rotation against the test structures. Since measurement contours serve as a reference, it is imperative that they are very well aligned to the test structures
2. Eliminate gaps such that contours can be written as polygons. Contour gaps or discontinuities have so far been limiting the choices of techniques used in cost functions for the OPC model calibration.
3. Field of view has to be larger than 3~5 um. This enables model to take into account long range effects of printing process.
4. The need to achieve precision/ accuracy comparable to CD measurement.
5. Line edge roughness issues. Unlike CD measurement, contours currently contain raw information about the line
6. edge roughness which degrades model quality statistics.