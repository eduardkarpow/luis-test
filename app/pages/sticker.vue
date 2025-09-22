<template>
    <div class="body">
        <div class="py-12 min-h-screen">
            <UContainer>
                <div class="mb-8">
                    <USkeleton class="h-8 w-1/2 mb-4" style="height: 2rem;" />
                    <USkeleton class="h-6 w-3/4" style="height: 1.5rem;" />
                </div>

                <div v-for="n in 50" :key="n" class="mb-6">
                    <UCard :key="n" class="mb-4" style="min-height: 100px;">
                        <div class="flex items-center gap-4">
                            <USkeleton class="h-12 w-12 rounded-full" style="height: 3rem; width: 3rem;" />
                            <div class="flex-1 space-y-2">
                                <USkeleton class="h-4 w-2/3" style="height: 1rem;" />
                                <USkeleton class="h-4 w-4/5" style="height: 1rem;" />
                            </div>
                        </div>

                        <div class="mt-4 space-y-2">
                            <USkeleton class="h-4 w-full" style="height: 1rem;" />
                            <USkeleton class="h-4 w-full" style="height: 1rem;" />
                            <USkeleton class="h-4 w-1/2" style="height: 1rem;" />
                        </div>
                    </UCard>
                </div>
            </UContainer>
        </div>
    </div>
    <side-sticker />
</template>

<style lang="scss" scoped>
.body {
    width: 100%;
    height: 150vh;
}
</style>