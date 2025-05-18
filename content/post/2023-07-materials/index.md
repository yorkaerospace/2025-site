+++
date = '2023-07-20T00:00:00+00:00'
draft = true
title = 'Material Choices for Model Rocketry'
image = 'banner.png'
tags = [
    "Manufacturing",
    "Materials"
]
+++
Throughout our journey in model rocketry, we've experimented with different materials for each part of our designs. Our choices have been moulded by all sorts of factors, such as the manufacturing processes we had available, cost and availability of the materials and the properties required for the task at hand. As such, we've learned a lot about the pros and cons of many materials, and in this article, we hope to pass on this knowledge to help you along your road into rocketry!
## Tubes

The body tube is the largest part of the rocket and needs to withstand the brunt of the force from the motor, supporting all of the other components. There are usually three main choices for rocket bodies: Cardboard, Phenolic and Fibreglass
### Cardboard

As weak as it can seem in the boxes and packaging you may encounter day to day, the vast majority of model rocket tubes are actually just cardboard! Our very first rockets started out with cardboard tubes, and we're still using them to this day! While your average cardboard tube is quite easy to compress or crush in the short axes, this direction can be reinforced with rings from inside - and isn't that important in a rocket anyway. In the long axis, cardboard tubes have excellent strength, and this is what we take advantage of in a rocket, where almost all the force is vertical.

You can buy cardboard tubes made specifically for model rocketry, but any old tube will work. Many of our rockets have been made out of old postal tubes!
### Phenolic

Phenolic can be seen as the next step up from cardboard tubes. It is a composite made up of the same fibres as cardboard but impregnated with resin, which is spiral-wrapped and heat cured. This creates a material with up to 5x the compressive strength of cardboard, along with better thermal properties too. It is however significantly more expensive than cardboard. We tend to use phenolic tubes as motor mounts, due to their high thermal resistance.
### Fibreglass

Fibreglass is an advanced composite material made from a fine lattice of thin glass fibres impregnated with epoxy resin. It's commonly found in boats, spanning kayaks to yachts - and it's excellent for rocketry too! Fibreglass tubes are at the forefront of model rocketry due to their excellent compressive strength from the epoxy, as well as tensile strength from the fibres. It's also relatively light, at about half the density of aluminium with a higher strength-to-weight ratio. We've used fibreglass for the tubes of all of our most powerful rockets. That said, fibreglass is more brittle than its alternatives and can crack or shatter under some conditions. It's also the most expensive option and is hazardous to work with due to both the sharp glass fibres, and the epoxy fumes. 

You can buy premade fibreglass tubes, or roll your own, as we covered in a [previous article]( {{< relref "2022-03-budget-fiberglass" >}})

As a footnote, carbon fibre can also be used in place of fibreglass but still has many of the same problems, though it is significantly lighter and stronger. It is also conductive, forming a Faraday cage, which may be inconvenient if you need to include a radio on your rocket.
## Machined Parts

Rockets often also require more complex parts, such as mounting points for the parachute lines, or containers for the avionics bay or payload. When machining these smaller but still critical parts, there are important tradeoffs to be considered.
### Steel

We generally avoid steel for rocket parts due to how heavy it is - despite its excellent strength. While we could make smaller components of equivalent strength using steel, less dense metals can have enough strength with lower total mass. Depending upon the grade of steel, it is also one of the more difficult materials to machine.
All this being said, it can be useful for sheet metal parts such as thin bulkheads which do not require threaded holes, as for a given thickness it is stiffer than aluminium. Steel nuts and bolts are also commonly used, as they have very high tensile strength, are readily available, and have fairly low mass to start with. In particular, the U-bolts to which the parachute lines are tied are almost invariably steel, as they need to be extremely strong.
### Aluminium

Aluminium is a common material used for rocket components, as well as across the aerospace and robotics industries as a whole. It is relatively strong for a given weight, is relatively light and is an easy material to machine with almost any tooling.
Aluminium is suitable for most high-strength components, particularly those exposed to high temperatures. We have used aluminium for the motor retainer, which takes the weight of the main body tube and motor when the parachute deploys (with about 20G of acceleration), and multiple bulkheads (which also take the weight of other components when parachutes are deployed). We've also used aluminium for external motor retainers, which have to sit right next to the motor's exhaust while being light enough to not unbalance the rocket.
### Delrin

Delrin is a popular industrial plastic designed to be strong and easy to machine. It is around half the density of aluminium, though it is weaker, particularly for small load-bearing threads. We avoid using it in larger rockets like Freyja, but it may be useful for making bulkheads and motor retainers for smaller rockets with less force on the parts. 

Something to be mindful of is that delrin will naturally have a very smooth surface, which makes it difficult for adhesives to bond to it. We have used Delrin on one rocket to date, and it fell apart in flight as the epoxy joints failed. Scoring or knurling the faces you intend to glue may help here, or we may have simply used the wrong adhesive.
### Brass

Brass is not generally used in rocket construction, due to its high density and relatively low strength-weight ratio. However, its high density is useful for components whose purpose is to be heavy, such as reaction wheels and ballast. For these applications, you need the highest possible density for the components in order to make the components as physically small for a given weight as possible. In the past, it was common to use scraps of lead as ballast for model rockets, although this has become less common due to its toxicity.

|Density|Strength|Machinability*|Applications|
|---|---|---|---|
|Steel 	|Very High (~8.0 g/cm³) 	|Excellent  (350 MPa) |	Okay 	|Thin plates, fixings|
|Aluminium| 	Moderate (~2.7 g/cm³) |	Good        (110 MPa) |	Good 	|Threaded parts, motor retainers.|
|Delrin |	Low          (~1.4 g/cm³) |	Good        (76 MPa) |	Excellent |	Large light parts, centring rings.|
|Brass |	Very High (~8.7 g/cm³) |	Very good (120 MPa) |	Good |	Ballast, Reaction Wheels|

*Machinability is based on our experience, on a very small lathe. Mileage will vary.
## Other Parts

The other parts of the rocket we're yet to cover are the nose cone, fins and centring rings. Fins can be made of fibreglass sheets as mentioned above, but there are other materials to consider:
### Plywood

Plywood fins can be surprisingly durable and is a straightforward material to work with - either with hand tools or with machines like a laser cutter. We've also used plywood for centring rings, which sit between the motor tube and the body tube to keep everything aligned. These only need a small amount of compressive strength to do their job, and the low density of wood is ideal at the tail end of the rocket so as not to offset the centre of gravity too much.
### 3D Printed PLA

3D printing is an extremely versatile manufacturing process which allows us to make very complex parts with ease. PLA is the default for any 3D printed part, as it's cheap, readily available, non-toxic and sufficiently strong for applications like PCB mounts, shells for payloads, and other parts that need complex geometry. It is, however, somewhat brittle, especially along layer lines, rather heavy, and melts at a low temperature. These aren’t massive issues for nosecones, but careful design is needed if you wish to 3d-print other parts. 
### Acrylic (Perspex)

We have used Acrylic in the past for components like fins and thrust rings, due to it being available to us through our university - but we found it was too brittle for most rocketry applications. Furthermore, it's also more dense than wood for fins, and not as strong as aluminium for thrust rings. Acrylic can be nice for aesthetic purposes, but we've decided to stay away ever since we lost the fins and cracked the thrust ring on our first mid-power rocket, Small Mike.
## Conclusion

The importance of material selection in the design of model rockets cannot be overstated. As a general rule, small rockets most likely will not require major components to be made out of metal, and will usually be fine with a cardboard tube and 3D-printed PLA nosecone.

However, it is usually a good idea for larger rockets to use aluminium for components like motor retainers and bulkheads and fibreglass for the body tube. We have not had much luck with 3D-printed nosecones on larger launches, such as Freyja, our competition rocket, as they tend to break along the layer lines when the rocket reaches the ground. Centring rings can still be laser cut out of ply, almost no matter how large the rocket is, as they take relatively little force.
