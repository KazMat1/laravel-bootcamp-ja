+++
title = 'hogehoge'
date = 2024-03-09T16:08:39+09:00
draft = false
+++

# はじめに
Laravel Bootcampへようこそ！このガイドでは、ゼロからモダンなLaravelアプリケーションを構築していきます。フレームワークを探索するために、*Chirper*というマイクロブログプラットフォームを構築していきましょう。

## 自分だけの冒険を選ぼう：Blade、Livewire、またはJavaScript

Laravelは非常に柔軟で、あなたのニーズに合わせた幅広い技術を使ってフロントエンドを構築できます。このチュートリアルでは、いくつかの選択肢を用意しました。

### Blade
[Blade](https://laravel.com/docs/blade)はLaravelに付属するシンプルでありながら強力なテンプレートエンジンです。HTMLはサーバーサイドでレンダリングされ、データベースからの動的なコンテンツを簡単に含めることができます。また、[Tailwind CSS](https://tailwindcss.com/)を使用して見栄えを良くします！

どこから始めればよいか分からない場合は、Bladeが最も直感的だと思います。LivewireやJavaScriptを使ってChirperを再構築することもできます。

```blade filename=welcome.blade.php
Greetings {{ $friend }}, let's build Chirper with Blade!

<a href="/blade/installation" class="group relative inline-flex border border-red-600 focus:outline-none mt-2 no-underline">
    <span class="w-full inline-flex items-center justify-center self-stretch px-4 py-2 text-sm text-red-600 text-center font-bold uppercase bg-white dark:bg-dark-700 ring-1 ring-red-600 ring-offset-1 dark:ring-offset-dark-600 transform transition-transform group-hover:-translate-y-1 group-hover:-translate-x-1 group-focus:-translate-y-1 group-focus:-translate-x-1">Build Chirper with Blade</span>
</a>


### Livewire

Livewireは、PHPだけを使って動的でリアクティブなフロントエンドUIを構築する強力な方法です。正直、JavaScriptではないと信じられないでしょう。Laravel開発者ならすぐに慣れることができます。


```php tab=Class filename=counter.blade.php
<?php

use Livewire\Volt\Component;

new class extends Component
{
    public int $count = 0;

    public function increment(): void
    {
        $this->count++;
    }
}; ?>

<div>
    <h1>{{ $count }}</h1>
    <button wire:click="increment">+</button>
</div>
```

```php tab=Functional filename=counter.blade.php
<?php

use function Livewire\Volt\{state};

state(['count' => 0]);

$increment = fn () => $this->count++;

?>

<div>
    <h1>{{ $count }}</h1>
    <button wire:click="increment">+</button>
</div>
```

<a href="/livewire/installation" class="group relative inline-flex border border-red-600 focus:outline-none mt-2 no-underline">
    <span class="w-full inline-flex items-center justify-center self-stretch px-4 py-2 text-sm text-red-600 text-center font-bold uppercase bg-white dark:bg-dark-700 ring-1 ring-red-600 ring-offset-1 dark:ring-offset-dark-600 transform transition-transform group-hover:-translate-y-1 group-hover:-translate-x-1 group-focus:-translate-y-1 group-focus:-translate-x-1">Build Chirper with Livewire</span>
</a>


### JavaScript & Inertia

JavaScriptを使用したい場合は、VueとReactの両方に対するコードサンプルを提供します。また、それらをすべてつなげるためにInertiaを使用し、Tailwind CSSで見栄えを良くします！

どちらを選択すべきか分からない場合、Vueは初心者に優しく、非常に強力であるため、私たちはVueの大ファンです。Bootcampを終えた後、他のスタックで再挑戦することができます。

好きなスタックを選んでください：

```vue tab=Vue filename=Welcome.vue
<template><!-- [tl! .hidden] -->
<Welcome>
    Hey {{ friend }}, let's build Chirper with Vue!
</Welcome>
</template><!-- [tl! .hidden] -->
```

```jsx tab=React filename=Welcome.jsx
<Welcome>
    Nice to see you {friend}, let's build Chirper with React!
</Welcome>
```

いつでもどちらかのフレームワークのコードを見て、もう一方の世界がどのようなものか確認できますが、プロジェクト内でコードを混ぜないようにしてください。

<a href="/inertia/installation" class="group relative inline-flex border border-red-600 focus:outline-none mt-2 no-underline"> <span class="w-full inline-flex items-center justify-center self-stretch px-4 py-2 text-sm text-red-600 text-center font-bold uppercase bg-white dark:bg-dark-700 ring-1 ring-red-600 ring-offset-1 dark:ring-offset-dark-600 transform transition-transform group-hover:-translate-y-1 group-hover:-translate-x-1 group-focus:-translate-y-1 group-focus:-translate-x-1">JavaScriptとInertiaでChirperを構築する</span> </a>


