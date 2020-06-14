# [AvatarMe: Realistically Renderable 3D Facial Reconstruction "in-the-wild"](https://arxiv.org/abs/2003.13845):
[![Youtube Video](https://img.shields.io/badge/HD%20Video-Results-lightgrey?logo=youtube)](https://www.youtube.com/watch?v=fEsgeZPN8Uw)
[![arXiv Prepring](https://img.shields.io/badge/arXiv-Preprint-lightgrey?logo=arxiv)](https://arxiv.org/pdf/2003.13845.pdf)

Public repository for the CVPR 2020 paper AvatarMe, with high resolution results, data and more.

[Alexandros Lattas](https://github.com/lattas)<sup> 1,2</sup>,
[Stylianos Moschoglou](https://www.doc.ic.ac.uk/~sm3515/)<sup> 1,2</sup>,
[Baris Gecer](http://barisgecer.github.io)<sup> 1,2</sup>,
[Stylianos Ploumpis](https://www.imperial.ac.uk/people/s.ploumpis)<sup> 1,2</sup>,
[Vasileios Triantafyllou](https://facesoft.io/company.html)<sup> 2</sup>,
<br/>
[Abhijeet Ghosh](https://www.doc.ic.ac.uk/~ghosh/)<sup> 1</sup>,
[Stefanos Zafeiriou](https://wp.doc.ic.ac.uk/szafeiri/)<sup> 1,2</sup>
<br/>
<sup>1 </sup>Imperial College London
<br/>
<sup>2 </sup>FaceSoft

__[[Paper PDF](http://openaccess.thecvf.com/content_CVPR_2020/papers/Lattas_AvatarMe_Realistically_Renderable_3D_Facial_Reconstruction_In-the-Wild_CVPR_2020_paper.pdf)]__
__[[CVPR 2020](http://cvpr20.com/event/avatarme-realistically-renderable-3d-facial-reconstruction-in-the-wild/)]__

### Overview

![Intro Image](img/avatarme_teaser.png "Teaser Image")

AvatarMe is the first method that is able to reconstruct photorealistic 3D faces from a single ‘in-the-wild” image with an increasing level of detail. To achieve this, we capture a large dataset of facial shape and reflectance and build on a state-of-the 3D texture and shape reconstruction method and successively refine its results in order to generate the high-resolution diffuse and specular components that are required for realistic rendering.

### Method

![Method Image](img/avatarme_method.png "Method Image")

A 3DMM is fitted to an ''in-the-wild'' input image 
and a completed UV texture is synthesized,
while optimizing for the identity match between the rendering and the input.
The texture is up-sampled 8 times,
to synthesize plausible high-frequency details.
We then use an image translation network to de-light the texture
and obtain the diffuse albedo with high-frequency details. 
Then, separate networks are used to infer the specular albedo,
diffuse normals and specular normals from the diffuse albedo and the 3DMM shape normals.
Moreover,
the networks are trained on 512x512 patches and inferences are ran on 1536x1536 patches with a sliding window.
Finally,
we can transfer the facial shape and the consistently inferred reflectance
to a head model.
Both face and head can be rendered realistically in any environment.

<p float="left">
  <img src="img/proc_diffAlb.gif" width="400" alt="Patch process for Diffuse Albedo" title="Patch process for Diffuse Albedo" hspace=20/>
  <img src="img/proc_specAlbs.gif" width="400" alt="Patch prosses for Specular Albedo" title="Patch prosses for Specular Albedo">
  <p> Patch process for Diffuse and Specular Abedo</p>
</p>
<p float="left">
  <img src="img/proc_diffNormals.gif" width="400" alt="Patch process for Diffuse Normals" title="Patch process for Diffuse Normals" hspace=20/>
  <img src="img/proc_specNorms.gif" width="400" alt="Patch process for Specular Normals" title="Patch process for Specular Normals"/>
  <p>Patch process for Diffuse and Specular Normals </p>
</p>

### Results

For high quality rendered results see the following youtube [video](https://www.youtube.com/watch?v=fEsgeZPN8Uw).

<a href="https://www.youtube.com/watch?v=fEsgeZPN8Uw">
   <img alt="Click for HD video results" src="img/teaser_image.gif" title="Click for HD video results" height=300>
</a>

<a href="https://www.youtube.com/watch?v=fEsgeZPN8Uw">
   <img alt="Click for HD video results" src="img/results_preview.gif" title="Click for HD video results">
</a>

### Data
Information about the public training data will be anounced as soon as possible.

### Citation
If you find this work useful, please use the following to cite our paper:
```
@article{lattas2020avatarme,
  title={AvatarMe: Realistically Renderable 3D Facial Reconstruction "in-the-wild"},
  author={Lattas, Alexandros and Moschoglou, Stylianos and Gecer, Baris and Ploumpis, Stylianos and Triantafyllou, Vasileios and Ghosh, Abhijeet and Zafeiriou, Stefanos},
  journal={arXiv preprint arXiv:2003.13845},
  year={2020}
}
```
