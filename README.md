# water-demand-projection-ml-pipeline

A pipeline combining Computer Vision (Roboflow Workflows/GPT-6 Astra) and Spatial Data Science (GeoPandas/Rasterio) to automate customer point detection and hydraulic headloss modeling for an 11.8 km water pipeline extension.
Manually tracing buildings from satellite imagery for infrastructure planning takes weeks and is prone to human error. This project reduces that timeline to minutes using Foundation AI models while preserving 100% spatial accuracy.

Process:
Step 1: Spatial discretization of imagery into 133 tiles using rasterio under EPSG:32630.
Step 2: Zero-shot building annotation via Roboflow Workflows using GPT-6 Astra, yielding 6,128 customer points.
Step 3: Affine spatial transformation to map abstract pixel boxes back to real-world UTM coordinates.
Step 4: Hydraulic modeling using the Hazen-Williams equation to calculate a design flow rate of 78.25 L/s and a friction headloss of 77.33 meters.

Results:
- 6,128 connection points generated automatically.
- 11.8 km pipeline routing analysis.
- Clear engineering insight: Identified that the downstream DN315 segment creates a 73% peak friction drop bottleneck, 
requiring a 9.0–10.0 Bar upstream dynamic pressure input.
