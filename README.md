
# Bytopea Demo

This project is a demo website built with Vue 3, Vite, and Tailwind CSS. It features a dynamic banner component with carousel functionality powered by Swiper.

## Website

Visit the live site: [https://bytopeaa.netlify.app/](https://bytopeaa.netlify.app/)

## Features
- Vue 3 with `<script setup>`
- Vite for fast development and build
- Tailwind CSS for utility-first styling
- Swiper integration for carousels
- Modular BannerComponent with support for images and CTAs

## Getting Started

1. **Install dependencies:**
	```sh
	npm install
	```
2. **Run the development server:**
	```sh
	npm run dev
	```
3. **Build for production:**
	```sh
	npm run build
	```

## Swiper Integration

Ensure the `swiper` package is installed. The build configuration marks `swiper`, `swiper/vue`, and `swiper/swiper-bundle.css` as external to resolve build issues.

## Project Structure

- `src/components/BannerComponent.vue`: Main banner/carousel component
- `src/App.vue`: Example usage of the banner component
- `vite.config.js`: Vite configuration with Swiper externals

## License

MIT
