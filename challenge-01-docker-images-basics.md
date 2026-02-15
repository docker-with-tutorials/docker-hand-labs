# Challenge 01 — Docker Images Basics

## Context

Docker images are immutable, layered filesystem snapshots used to create containers.  
Every container starts from an image, but understanding how images are structured is essential before working with more advanced container concepts.

This challenge focuses on understanding how Docker images are built, stored, and referenced.

---

## Scenario

You are given a simple Dockerfile in this repository.

Your goal is to analyze and interact with Docker images to understand:

- How images are built
- How layers are created
- How tags work
- The difference between tags and digests
- The relationship between images and containers

---

## Tasks

### 1. Inspect Existing Images

Run:

```bash
docker images
```

Questions:

- What images are currently available on your system?
- What is the difference between IMAGE ID and TAG?
- What does the SIZE column represent?

### 2. Pull an Official Image

Pull a small image:

```bash
docker pull alpine
```

After pulling:

```bash
docker images
```

Questions:

- What tag was assigned by default?
- What changed in your local image list?
- What is the IMAGE ID associated with alpine?

### 3. Inspect the Image

Run:

```bash
docker inspect alpine
```

Questions:

- What is the image digest?
- What is the default command (Cmd)?
- What architecture is the image built for?

### 4. Analyze Image Layers

Run:

```bash
docker history alpine
```

Questions:

- How many layers does the image have?
- Which layers are empty?
- What does this tell you about how images are built?

### 5. Tag the Image

Create a new tag:

```bash
docker tag alpine alpine:lab
```

Then check:

```bash
docker images
```

Questions:

- Did Docker create a new image or just a new reference?
- Do both tags share the same IMAGE ID?
- Expected Understanding

By the end of this challenge, you should clearly understand:

- An image is immutable.
- Tags are just references to an image ID.
- Images are composed of layers.
- Containers are runtime instances created from images.
