# 1D Sedimentation of a Sphere under Gravity (CFD – OpenFOAM)
CFD simulation of a sedimenting sphere using OpenFOAM (sedFoam, overset mesh, 6DoF)

## 📌 Overview
This project simulates the **sedimentation of a single sphere in a viscous fluid under gravity**, 
using the **sedFoam multiphase solver** in OpenFOAM.  
The work replicates the **benchmark experiments of ten Cate et al. (2002)**, 
demonstrating how overset meshes and six-degree-of-freedom (6DoF) dynamics can 
accurately model particle–fluid interactions.

Recruiter note: This project highlights my **CFD simulation skills, numerical modeling expertise, 
and hands-on experience with OpenFOAM** for fluid–particle systems.  

---

## 🎯 Objectives
- Validate CFD results against **experimental data (ten Cate et al., 2002)**.  
- Capture full sedimentation dynamics: acceleration, terminal velocity, near-wall effects.  
- Demonstrate use of **overset mesh** + **6DoF rigid body motion** for moving particles.  

---

## 🛠️ Simulation Setup
- **Domain**: Rectangular tank (100 × 100 × 160 mm³)  
- **Sphere**: Diameter = 15 mm, initial height = 120 mm  
- **Mesh**:  
  - `blockMesh` (tank) + `snappyHexMesh` (sphere)  
  - Overset interpolation between background & sphere meshes  
- **Solver**: `overSedDymFoam_rbgh` (sedFoam + 6DoF motion)  
- **Physics**:  
  - Fluid density ≈ 970–960 kg/m³, viscosity = 373 mPa·s  
  - Sphere density = 1120 kg/m³  
  - Gravity downward (−z)  

---

## 📊 Results
- **Trajectory**: Sphere accelerates, reaches steady terminal velocity ~−0.028 m/s.  
- **Velocity evolution**: Matches experimental trends; steady-state reached ≈ 0.5 s.  
- **Flow field**: Vortex structures + wake patterns align with published PIV data.  

Key observations:
- Mean error in velocity ≈ 14%, max error ≈ 34%  
- Errors mainly near wall approach (unmodeled lubrication forces)  

👉 Overall, results validate the solver setup and demonstrate CFD accuracy at low Reynolds number (Re ≈ 1.5).  

---

## 📂 Repository Contents
- `report/` → Detailed project PDF with methodology & analysis  
- `results/` → Simulation images, contour plots, velocity trajectories  
- `setup/` → Case setup (meshing, boundary conditions)  
- `references/` → Key literature (e.g., ten Cate et al., 2002)  

---

## 🚀 Skills Demonstrated
- OpenFOAM (sedFoam, 6DoF motion, overset meshes)  
- CFD modeling of particle–fluid interaction  
- Validation of numerical simulations with experimental data  
- Mesh generation: blockMesh, snappyHexMesh  
- Data analysis: velocity, trajectory, wake structures  

---

## 📚 References
- ten Cate, J.A.M., et al. (2002). *Particle image velocimetry experiments and lattice-Boltzmann simulations on a single sphere settling under gravity.* Physics of Fluids.  
- [OpenFOAM Wiki – Settling Sphere Benchmark](https://wiki.openfoam.com/Settling_Sphere_by_Michael_Alletto)

---

## 📜 License
This project is released under the **MIT License** – free to use and adapt.
