# roadmap for the metamorphosis nft project

1. [ ] make the art

2. [ ] write the code

3. [ ] deploy on testnet

4. [ ] deploy on mainnet


## 1 [ ] Make the Art

Making the art will be 95% of the work. First I need to figure out what art to make, and figure out the level of automation involved in the generation of the art. I need to know how many pieces, and how many variations.

Let's think this through. I think that there can be essentially subcollections within this collection, or let's call them `series`. These parameters that I'm outlining in this stage are crucial to also determining the metadata. I'm thinking that each `series` will have a `series_name` which is a single word noun that represents a common thing that goes through a metamorphosis. These are essentially sub collections.

```rust

struct Series {
    series_name: String,
    series_number: u8,
    series_length: Seconds,
    series_size: u8,
}
```

Can I have a type be seconds?

If so, then I would make a custom type called `Seconds` that would constrain the `series_length` field by 12, where we can have 1, 2, 3, 4, and 5 second series. This means series range in length from 12 to 60 `frames`. `frames` are template drawings without color or stylization, or any addons. They are the pure animation.

We can have the following series at a minimum:

1. butterfly
2. phoenix
3. city
4. tree
5. machine
6. baby
7. adult
8. human
9. volcano
10. land

This could allow for a lot of variety and a fairly sizeable collection.

> Assume each series is 3 seconds. Animating on twos for a 3 second loop would be 36 (3 x 12 frames per second). This means that just the animations alone with no variations would yield 360 NFTs.

> If we assume that each series has several traits, we can assume that we can easily produce around 10 variations of each animation, resulting in 3,600 NFTs. Let's keep the math simple so that I can focus on the art, as opposed to the math with Sentry Nodes which is part of the challenge with that project.

> If someone collects one of each of the unique frames in a series, they can burn the whole collection to generate an animated, infinite loop with their nfts. the burned nfts are gone forever.

## Art Style and Tools

For the art, I'm thinking that Aesprite should be the only tool used, and that the size of each image should be a fixed 100 x 100 pixel image, upscaled 5x. This will reduce the complexity required in the art, and could produce a cohesive art style.

Each series should have a unified and cohesive, but separate color scheme. I need to so some color research, but I will also probably make ample use of chatGPT to help with some clean and distinct color palletes for each of the series.

## Workflow

1. Create each series base template first.
2. Figure out the layers for each series
3. Use hashlips art engine to generate all of the variations, frame by frame.




