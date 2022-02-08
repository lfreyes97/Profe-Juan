<template>
<header class="h-24 sm:h-32 flex items-center z-30 w-full">
        <div class="container mx-auto px-6 flex items-center justify-between">
            <div class="uppercase text-gray-800 dark:text-white font-black text-3xl">
                <h1>
                Prof. Juan C. Reyes
                </h1>
            </div>
            <div class="flex items-center">
                <nav class="font-sen text-gray-800 dark:text-white uppercase text-lg lg:flex items-center hidden">
                    <nuxt-link to="/" class="py-2 px-6 flex hover:text-blue-700">Inicio</nuxt-link>
                    <nuxt-link to="/blog" class="py-2 px-6 flex hover:text-blue-700">Blog</nuxt-link>
                    <nuxt-link to="/libros" class="py-2 px-6 flex hover:text-blue-700">Libros</nuxt-link>
                    <nuxt-link to="/materiales" class="py-2 px-6 flex hover:text-blue-700">Materiales</nuxt-link>
                    <nuxt-link to="/actividades" class="py-2 px-6 flex hover:text-blue-700">Actividades</nuxt-link>
                </nav>
            </div>
        </div>
    </header>
</template>