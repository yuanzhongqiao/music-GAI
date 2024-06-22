<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">状态：</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">存档（代码按原样提供，无需更新）</font></font></p>
<div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">点唱机</font></font></h1><a id="user-content-jukebox" class="anchor" aria-label="永久链接：点唱机" href="#jukebox"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“点唱机：音乐生成模型”的代码</font></font></p>
<p dir="auto"><a href="https://arxiv.org/abs/2005.00341" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Paper </font></font></a>
<a href="https://openai.com/blog/jukebox" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Blog </font></font></a>
<a href="http://jukebox.openai.com/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Explorer </font></font></a>
<a href="https://colab.research.google.com/github/openai/jukebox/blob/master/jukebox/Interacting_with_Jukebox.ipynb" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Colab</font></font></a></p>
<div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装</font></font></h1><a id="user-content-install" class="anchor" aria-label="永久链接：安装" href="#install"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><a href="https://docs.conda.io/en/latest/miniconda.html" rel="nofollow"><font style="vertical-align: inherit;">从https://docs.conda.io/en/latest/miniconda.html</font></a><font style="vertical-align: inherit;">安装 conda 包管理器</font></font><a href="https://docs.conda.io/en/latest/miniconda.html" rel="nofollow"><font style="vertical-align: inherit;"></font></a></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code># Required: Sampling
conda create --name jukebox python=3.7.5
conda activate jukebox
conda install mpi4py=3.0.3 # if this fails, try: pip install mpi4py==3.0.3
conda install pytorch=1.4 torchvision=0.5 cudatoolkit=10.0 -c pytorch
git clone https://github.com/openai/jukebox.git
cd jukebox
pip install -r requirements.txt
pip install -e .

# Required: Training
conda install av=7.0.01 -c conda-forge 
pip install ./tensorboardX
 
# Optional: Apex for faster training with fused_adam
conda install pytorch=1.1 torchvision=0.3 cudatoolkit=10.0 -c pytorch
pip install -v --no-cache-dir --global-option="--cpp_ext" --global-option="--cuda_ext" ./apex
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="# Required: Sampling
conda create --name jukebox python=3.7.5
conda activate jukebox
conda install mpi4py=3.0.3 # if this fails, try: pip install mpi4py==3.0.3
conda install pytorch=1.4 torchvision=0.5 cudatoolkit=10.0 -c pytorch
git clone https://github.com/openai/jukebox.git
cd jukebox
pip install -r requirements.txt
pip install -e .

# Required: Training
conda install av=7.0.01 -c conda-forge 
pip install ./tensorboardX
 
# Optional: Apex for faster training with fused_adam
conda install pytorch=1.1 torchvision=0.3 cudatoolkit=10.0 -c pytorch
pip install -v --no-cache-dir --global-option=&quot;--cpp_ext&quot; --global-option=&quot;--cuda_ext&quot; ./apex" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">采样</font></font></h1><a id="user-content-sampling" class="anchor" aria-label="固定链接：采样" href="#sampling"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从头开始采样</font></font></h2><a id="user-content-sampling-from-scratch" class="anchor" aria-label="永久链接：从头开始采样" href="#sampling-from-scratch"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要正常采样，请运行以下命令。模型可以是</font></font><code>5b</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>5b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>1b_lyrics</code></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>python jukebox/sample.py --model=5b_lyrics --name=sample_5b --levels=3 --sample_length_in_seconds=20 \
--total_sample_length_in_seconds=180 --sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python jukebox/sample.py --model=5b_lyrics --name=sample_5b --levels=3 --sample_length_in_seconds=20 \
--total_sample_length_in_seconds=180 --sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>python jukebox/sample.py --model=1b_lyrics --name=sample_1b --levels=3 --sample_length_in_seconds=20 \
--total_sample_length_in_seconds=180 --sr=44100 --n_samples=16 --hop_fraction=0.5,0.5,0.125
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python jukebox/sample.py --model=1b_lyrics --name=sample_1b --levels=3 --sample_length_in_seconds=20 \
--total_sample_length_in_seconds=180 --sr=44100 --n_samples=16 --hop_fraction=0.5,0.5,0.125" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以上代码生成</font></font><code>sample_length_in_seconds</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">一首歌曲的前几秒音频，歌曲总长度为</font></font><code>total_sample_length_in_seconds</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。要使用多个 GPU，请按</font></font><code>mpiexec -n {ngpus} python jukebox/sample.py ...</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如下方式启动上述脚本，以便它们使用</font></font><code>{ngpus}</code></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从每个级别解码的样本存储在 中</font></font><code>{name}/level_{level}</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。您还可以在 下以 html 形式查看样本，其中包含对齐的歌词</font></font><code>{name}/level_{level}/index.html</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。通过服务器运行</font></font><code>python -m http.server</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并打开 html，以查看歌曲播放时歌词的动画。</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
所有采样数据（包括 zs、x、labels 和 samples_kwargs）的摘要都存储在 中</font></font><code>{name}/level_{level}/data.pth.tar</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">hps 适用于具有 16 GB GPU 内存的 V100 GPU。</font></font><code>1b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>5b</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>5b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">顶层先验分别占用 3.8 GB、10.3 GB 和 11.5 GB。存储转换器键、值缓存的峰值内存使用量约为每个样本 400 MB</font></font><code>1b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和 1 GB </font></font><code>5b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。如果您遇到 CUDA OOM 问题，请尝试</font></font><code>1b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或减少</font></font><code>max_batch_size</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">sample.py 和</font></font><code>--n_samples</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">脚本调用中的值。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 V100 上，需要大约 3 小时才能完全采样 20 秒的音乐。由于这是一个很长的时间，因此建议使用，</font></font><code>n_samples &gt; 1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以便您可以并行生成尽可能多的样本。1B 歌词和升采样器一次可以处理 16 个样本，而 5B 最多只能容纳 3 个。由于绝大多数时间都花在了升采样上，我们建议使用小于 16 的 3 的倍数，例如</font></font><code>--n_samples 15</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font><code>5b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这将使顶层以三组为一组生成样本，而升采样一次完成。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要继续从已生成的代码中采样更长时间，您可以运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>python jukebox/sample.py --model=5b_lyrics --name=sample_5b --levels=3 --mode=continue \
--codes_file=sample_5b/level_0/data.pth.tar --sample_length_in_seconds=40 --total_sample_length_in_seconds=180 \
--sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python jukebox/sample.py --model=5b_lyrics --name=sample_5b --levels=3 --mode=continue \
--codes_file=sample_5b/level_0/data.pth.tar --sample_length_in_seconds=40 --total_sample_length_in_seconds=180 \
--sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这里，我们取第一次采样运行中保存的 20 秒样本</font></font><code>sample_5b/level_0/data.pth.tar</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，然后继续添加 20 秒。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您也可以直接从级别 2 保存的输出继续，只需传递</font></font><code>--codes_file=sample_5b/level_2/data.pth.tar</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。请注意，这将在最后对完整的 40 秒歌曲进行上采样。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果你只在第一级停止采样，并希望对保存的代码进行上采样，你可以运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>python jukebox/sample.py --model=5b_lyrics --name=sample_5b --levels=3 --mode=upsample \
--codes_file=sample_5b/level_2/data.pth.tar --sample_length_in_seconds=20 --total_sample_length_in_seconds=180 \
--sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python jukebox/sample.py --model=5b_lyrics --name=sample_5b --levels=3 --mode=upsample \
--codes_file=sample_5b/level_2/data.pth.tar --sample_length_in_seconds=20 --total_sample_length_in_seconds=180 \
--sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里，我们取第一次采样运行中保存的 20 秒样本，</font></font><code>sample_5b/level_2/data.pth.tar</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并对较低的两个级别进行上采样。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用你自己的音乐提示</font></font></h2><a id="user-content-prompt-with-your-own-music" class="anchor" aria-label="永久链接：用你自己的音乐提示" href="#prompt-with-your-own-music"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果你想用自己的创作作品或任何其他音乐来提示模型，首先将它们保存为波形文件并运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>python jukebox/sample.py --model=5b_lyrics --name=sample_5b_prompted --levels=3 --mode=primed \
--audio_file=path/to/recording.wav,awesome-mix.wav,fav-song.wav,etc.wav --prompt_length_in_seconds=12 \
--sample_length_in_seconds=20 --total_sample_length_in_seconds=180 --sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="python jukebox/sample.py --model=5b_lyrics --name=sample_5b_prompted --levels=3 --mode=primed \
--audio_file=path/to/recording.wav,awesome-mix.wav,fav-song.wav,etc.wav --prompt_length_in_seconds=12 \
--sample_length_in_seconds=20 --total_sample_length_in_seconds=180 --sr=44100 --n_samples=6 --hop_fraction=0.5,0.5,0.125" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这将加载四个文件，将它们平铺以填充</font></font><code>n_samples</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">批次大小，并在前几秒启动模型</font></font><code>prompt_length_in_seconds</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">训练</font></font></h1><a id="user-content-training" class="anchor" aria-label="固定链接：培训" href="#training"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">向量量化差分自适应编码器</font></font></h2><a id="user-content-vqvae" class="anchor" aria-label="固定链接：VQVAE" href="#vqvae"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要训&ZeroWidthSpace;&ZeroWidthSpace;练小型 vqvae，请运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=small_vqvae --name=small_vqvae --sample_length=262144 --bs=4 \
--audio_files_dir={audio_files_dir} --labels=False --train --aug_shift --aug_blend
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=small_vqvae --name=small_vqvae --sample_length=262144 --bs=4 \
--audio_files_dir={audio_files_dir} --labels=False --train --aug_shift --aug_blend" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这里，</font></font><code>{audio_files_dir}</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是您可以放置&ZeroWidthSpace;&ZeroWidthSpace;数据集音频文件的目录，是</font></font><code>{ngpus}</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您要用于训练的 GPU 数量。以上使用 训练了两级 VQ-VAE </font></font><code>downs_t = (5,3)</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，这</font></font><code>strides_t = (2, 2)</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">意味着我们对音频进行下采样以</font></font><code>2**5 = 32</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">获得第一级代码，并</font></font><code>2**8 = 256</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">获得第二级代码。</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
检查点存储在</font></font><code>logs</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文件夹中。您可以通过运行 Tensorboard 来监控训练</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>tensorboard --logdir logs
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="tensorboard --logdir logs" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">事先的</font></font></h2><a id="user-content-prior" class="anchor" aria-label="固定链接：先前" href="#prior"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">训练先前或上采样器</font></font></h3><a id="user-content-train-prior-or-upsamplers" class="anchor" aria-label="永久链接：训练先验或上采样器" href="#train-prior-or-upsamplers"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">一旦 VQ-VAE 训练完成，我们就可以从其保存的检查点恢复它，并在学习的代码上训练先验。为了训练顶层先验，我们可以运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=small_vqvae,small_prior,all_fp16,cpu_ema --name=small_prior \
--sample_length=2097152 --bs=4 --audio_files_dir={audio_files_dir} --labels=False --train --test --aug_shift --aug_blend \
--restore_vqvae=logs/small_vqvae/checkpoint_latest.pth.tar --prior --levels=2 --level=1 --weight_decay=0.01 --save_iters=1000
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=small_vqvae,small_prior,all_fp16,cpu_ema --name=small_prior \
--sample_length=2097152 --bs=4 --audio_files_dir={audio_files_dir} --labels=False --train --test --aug_shift --aug_blend \
--restore_vqvae=logs/small_vqvae/checkpoint_latest.pth.tar --prior --levels=2 --level=1 --weight_decay=0.01 --save_iters=1000" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为了训练上采样器，我们可以运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=small_vqvae,small_upsampler,all_fp16,cpu_ema --name=small_upsampler \
--sample_length=262144 --bs=4 --audio_files_dir={audio_files_dir} --labels=False --train --test --aug_shift --aug_blend \
--restore_vqvae=logs/small_vqvae/checkpoint_latest.pth.tar --prior --levels=2 --level=0 --weight_decay=0.01 --save_iters=1000
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=small_vqvae,small_upsampler,all_fp16,cpu_ema --name=small_upsampler \
--sample_length=262144 --bs=4 --audio_files_dir={audio_files_dir} --labels=False --train --test --aug_shift --aug_blend \
--restore_vqvae=logs/small_vqvae/checkpoint_latest.pth.tar --prior --levels=2 --level=0 --weight_decay=0.01 --save_iters=1000" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们通过</font></font><code>sample_length = n_ctx * downsample_of_level</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，以便在下采样后，标记与先前 hps 的 n_ctx 匹配。这里，</font></font><code>n_ctx = 8192</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和分别</font></font><code>downsamples = (32, 256)</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">给出</font></font><code>sample_lengths = (8192 * 32, 8192 * 256) = (65536, 2097152)</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">底层和顶层。</font></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">学习率退火</font></font></h3><a id="user-content-learning-rate-annealing" class="anchor" aria-label="永久链接：学习率退火" href="#learning-rate-annealing"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为了获得最佳样本质量，请在训练结束时将学习率退火至 0。为此，请从最新的检查点继续训练并运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>--restore_prior="path/to/checkpoint" --lr_use_linear_decay --lr_start_linear_decay={already_trained_steps} --lr_decay={decay_steps_as_needed}
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="--restore_prior=&quot;path/to/checkpoint&quot; --lr_use_linear_decay --lr_start_linear_decay={already_trained_steps} --lr_decay={decay_steps_as_needed}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重复使用预先训练的 VQ-VAE 并从头开始在新数据集上训练顶层先验。</font></font></h3><a id="user-content-reuse-pre-trained-vq-vae-and-train-top-level-prior-on-new-dataset-from-scratch" class="anchor" aria-label="永久链接：重复使用预先训练的 VQ-VAE 并从头开始在新数据集上训练顶层先验。" href="#reuse-pre-trained-vq-vae-and-train-top-level-prior-on-new-dataset-from-scratch"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">无标签训练</font></font></h4><a id="user-content-train-without-labels" class="anchor" aria-label="永久链接：无标签训练" href="#train-without-labels"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们预先训练的 VQ-VAE 可以为各种类型的音乐生成压缩代码，而预先训练的上采样器可以将它们上采样回听起来非常类似于原始音频的音频。要将这些重新用于您选择的新数据集，您可以只重新训练顶层</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要在新数据集上进行顶层训练，请运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,small_prior,all_fp16,cpu_ema --name=pretrained_vqvae_small_prior \
--sample_length=1048576 --bs=4 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=False --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,small_prior,all_fp16,cpu_ema --name=pretrained_vqvae_small_prior \
--sample_length=1048576 --bs=4 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=False --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">训练</font></font><code>small_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">批次大小为 2、4 和 8 的模型分别需要 6.7 GB、9.3 GB 和 15.8 GB 的 GPU 内存。当数据集是同质的（例如所有钢琴曲、相同风格的歌曲等）时，几天到一周的训练通常可以产生合理的样本。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在训练即将结束时，按照</font></font><a href="#learning-rate-annealing"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下步骤</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将学习率退火至 0</font></font></p>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">新模型样本</font></font></h4><a id="user-content-sample-from-new-model" class="anchor" aria-label="永久链接：新模型示例" href="#sample-from-new-model"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">然后，您可以运行 sample.py，将我们模型的顶层替换为您的新模型。为此，</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"></font><code>my_model=("vqvae", "upsampler_level_0", "upsampler_level_1", "small_prior")</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在</font></font><code>MODELS</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中</font><font style="vertical-align: inherit;">添加条目</font></font><code>make_models.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更新</font></font><code>small_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字典</font></font><code>hparams.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以包含</font></font><code>restore_prior='path/to/checkpoint'</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。如果你直接在命令行脚本中更改了任何 hps（例如</font></font><code>heads</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：），请确保也在字典中更新它们，以便</font></font><code>make_models</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">正确恢复我们的检查点。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">按照采样部分所述运行sample.py，但现在使用</font></font><code>--model=my_model</code></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例如，假设我们</font><font style="vertical-align: inherit;">在 下训练了</font></font><code>small_vqvae</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>small_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font><font style="vertical-align: inherit;">。在 中</font><font style="vertical-align: inherit;">，我们将新模型的元组声明为</font><font style="vertical-align: inherit;">。</font></font><code>small_upsampler</code><font style="vertical-align: inherit;"></font><code>/path/to/jukebox/logs</code><font style="vertical-align: inherit;"></font><code>make_models.py</code><font style="vertical-align: inherit;"></font><code>my_model</code><font style="vertical-align: inherit;"></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>MODELS = {
    '5b': ("vqvae", "upsampler_level_0", "upsampler_level_1", "prior_5b"),
    '5b_lyrics': ("vqvae", "upsampler_level_0", "upsampler_level_1", "prior_5b_lyrics"),
    '1b_lyrics': ("vqvae", "upsampler_level_0", "upsampler_level_1", "prior_1b_lyrics"),
    'my_model': ("my_small_vqvae", "my_small_upsampler", "my_small_prior"),
}
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="MODELS = {
    '5b': (&quot;vqvae&quot;, &quot;upsampler_level_0&quot;, &quot;upsampler_level_1&quot;, &quot;prior_5b&quot;),
    '5b_lyrics': (&quot;vqvae&quot;, &quot;upsampler_level_0&quot;, &quot;upsampler_level_1&quot;, &quot;prior_5b_lyrics&quot;),
    '1b_lyrics': (&quot;vqvae&quot;, &quot;upsampler_level_0&quot;, &quot;upsampler_level_1&quot;, &quot;prior_1b_lyrics&quot;),
    'my_model': (&quot;my_small_vqvae&quot;, &quot;my_small_upsampler&quot;, &quot;my_small_prior&quot;),
}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">接下来，在 中，我们将它们与相应的</font><font style="vertical-align: inherit;">路径以及训练期间使用的任何其他命令行选项一起</font></font><code>hparams.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">添加到注册表中。另一个重要的注意事项是，对于具有歌词条件的顶级先验，我们必须找到一个自注意力层，以显示歌词和音乐标记之间的对齐。查找 为</font><font style="vertical-align: inherit;">6 或 7 的层。如果您的模型开始跟着歌词唱歌，则意味着某些层、头部对已经学会了对齐。恭喜！</font></font><code>restore_</code><font style="vertical-align: inherit;"></font><code>prior.prior.transformer._attn_mods[layer].attn_func</code><font style="vertical-align: inherit;"></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>my_small_vqvae = Hyperparams(
    restore_vqvae='/path/to/jukebox/logs/small_vqvae/checkpoint_some_step.pth.tar',
)
my_small_vqvae.update(small_vqvae)
HPARAMS_REGISTRY["my_small_vqvae"] = my_small_vqvae

my_small_prior = Hyperparams(
    restore_prior='/path/to/jukebox/logs/small_prior/checkpoint_latest.pth.tar',
    level=1,
    labels=False,
    # TODO For the two lines below, if `--labels` was used and the model is
    # trained with lyrics, find and enter the layer, head pair that has learned
    # alignment.
    alignment_layer=47,
    alignment_head=0,
)
my_small_prior.update(small_prior)
HPARAMS_REGISTRY["my_small_prior"] = my_small_prior

my_small_upsampler = Hyperparams(
    restore_prior='/path/to/jukebox/logs/small_upsampler/checkpoint_latest.pth.tar',
    level=0,
    labels=False,
)
my_small_upsampler.update(small_upsampler)
HPARAMS_REGISTRY["my_small_upsampler"] = my_small_upsampler
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="my_small_vqvae = Hyperparams(
    restore_vqvae='/path/to/jukebox/logs/small_vqvae/checkpoint_some_step.pth.tar',
)
my_small_vqvae.update(small_vqvae)
HPARAMS_REGISTRY[&quot;my_small_vqvae&quot;] = my_small_vqvae

my_small_prior = Hyperparams(
    restore_prior='/path/to/jukebox/logs/small_prior/checkpoint_latest.pth.tar',
    level=1,
    labels=False,
    # TODO For the two lines below, if `--labels` was used and the model is
    # trained with lyrics, find and enter the layer, head pair that has learned
    # alignment.
    alignment_layer=47,
    alignment_head=0,
)
my_small_prior.update(small_prior)
HPARAMS_REGISTRY[&quot;my_small_prior&quot;] = my_small_prior

my_small_upsampler = Hyperparams(
    restore_prior='/path/to/jukebox/logs/small_upsampler/checkpoint_latest.pth.tar',
    level=0,
    labels=False,
)
my_small_upsampler.update(small_upsampler)
HPARAMS_REGISTRY[&quot;my_small_upsampler&quot;] = my_small_upsampler" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用标签进行训练</font></font></h4><a id="user-content-train-with-labels" class="anchor" aria-label="永久链接：使用标签进行训练" href="#train-with-labels"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要使用您自己的音频文件元数据进行训练，请实现</font></font><code>get_metadata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以</font></font><code>data/files_dataset.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">返回
给定音频文件的</font></font><code>artist</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>genre</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。目前，您可以传递</font></font><code>''</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">lyrics 以不使用任何歌词。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于带标签的训练，我们将</font></font><code>small_labelled_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 中使用</font></font><code>hparams.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，并设置</font></font><code>labels=True,labels_v3=True</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。我们使用两种标签信息：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">艺术家/流派：
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于每个文件，我们返回一个 artist_id 和一个 gentle_id 列表。我们有一个列表而不是单个 gentle_id 的原因是，在 v2 中，我们将类型拆分</font></font><code>blues_rock</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为一个词袋</font></font><code>[blues, rock]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，并将
</font></font><code>max_bow_genre_size</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">其中大部分传递进去，</font></font><code>v3</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们将其视为单个单词并设置</font></font><code>max_bow_genre_size=1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更新</font></font><code>v3_artist_ids</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并</font></font><code>v3_genre_ids</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用新数据集中的 ID。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 中</font></font><code>small_labelled_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，设置 hps</font></font><code>y_bins = (number_of_genres, number_of_artists)</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>max_bow_genre_size=1</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></li>
</ul>
</li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">定时：
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于每个音频块，我们返回</font></font><code>total_length</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">歌曲的 、</font></font><code>offset</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当前音频块的 以及</font></font><code>sample_length</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">音频块的 。我们有三个时间嵌入：总长度、我们的当前位置以及我们当前位置占总长度的百分比，我们将这些值的范围划分为</font></font><code>t_bins</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">离散的箱体。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 中</font></font><code>small_labelled_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，将 hps</font></font><code>min_duration</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>max_duration</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设置为您想要的数据集的音频文件的最短/最长持续时间，以及</font></font><code>t_bins</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您想要将时间信息分散到多少个 bin 中。注意，
</font></font><code>min_duration * sr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">至少需要</font></font><code>sample_length</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">有一个音频块。</font></font></li>
</ul>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">完成这些修改后，要训练带标签的顶层模型，请运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,small_labelled_prior,all_fp16,cpu_ema --name=pretrained_vqvae_small_prior_labels \
--sample_length=1048576 --bs=4 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=True --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,small_labelled_prior,all_fp16,cpu_ema --name=pretrained_vqvae_small_prior_labels \
--sample_length=1048576 --bs=4 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=True --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于采样，请遵循与</font></font><a href="#sample-from-new-model"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">上述</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">相同的说明，但使用</font></font><code>small_labelled_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">而不是</font></font><code>small_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">带歌词的火车</font></font></h4><a id="user-content-train-with-lyrics" class="anchor" aria-label="永久链接：带歌词的火车" href="#train-with-lyrics"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要使用歌词进行训练，请更新</font></font><code>get_metadata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以</font></font><code>data/files_dataset.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">返回</font></font><code>lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。要使用歌词进行训练，我们将</font></font><code>small_single_enc_dec_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用</font></font><code>hparams.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">歌词：
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"></font><code>n_tokens</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于每个文件，我们将歌词字符与音频线性对齐，找到与音频块中点相对应的歌词位置，并传递以该位置为中心的歌词字符</font><font style="vertical-align: inherit;">窗口。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 中</font></font><code>small_single_enc_dec_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，将 hps</font></font><code>use_tokens=True</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>n_tokens</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设置为音频块使用的歌词字符数。根据</font></font><code>sample_length</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您正在训练的 进行设置，使其足够大，以至于音频块的歌词几乎总是可以在此大小的窗口内找到。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您使用非英语词汇，请</font></font><code>text_processor.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用新词汇进行更新并
</font></font><code>n_vocab = number of characters in vocabulary</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 中进行相应设置</font></font><code>small_single_enc_dec_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。在 v2 中，我们有一个</font></font><code>n_vocab=80</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
，而在 v3 中，我们错过了</font></font><code>+</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">等</font></font><code>n_vocab=79</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字符。</font></font></li>
</ul>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">完成这些修改后，要训练带有标签和歌词的顶层模型，请运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,small_single_enc_dec_prior,all_fp16,cpu_ema --name=pretrained_vqvae_small_single_enc_dec_prior_labels \
--sample_length=786432 --bs=4 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=True --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,small_single_enc_dec_prior,all_fp16,cpu_ema --name=pretrained_vqvae_small_single_enc_dec_prior_labels \
--sample_length=786432 --bs=4 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=True --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为了简化 hps 选择，我们在这里使用了一个</font></font><code>single_enc_dec</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">类似</font></font><code>1b_lyrics</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">模型的模型，该模型将转换器的编码器和解码器合并为一个模型。我们通过将歌词词汇和 vq-vae 词汇合并为一个更大的词汇，并将歌词标记和 vq-vae 代码展平为长度为 的单个序列来实现这一点</font></font><code>n_ctx + n_tokens</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。这使用了</font></font><code>attn_order=12</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包括</font></font><code>prime_attention</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来自歌词的键/值和来自音频的查询的层。如果您想使用具有通常的编码器-解码器样式转换器的模型，请使用</font></font><code>small_sep_enc_dec_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对于采样，请遵循与</font></font><a href="#sample-from-new-model"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">上述</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">相同的说明，但使用</font></font><code>small_single_enc_dec_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">而不是
</font></font><code>small_prior</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。为了在保存的 html 中获取歌词和样本之间的对齐，您需要</font><font style="vertical-align: inherit;">在 中设置</font></font><code>alignment_layer</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
和</font><font style="vertical-align: inherit;">。要找到最适合使用的层/头，请在训练示例上运行前向传递，保存所有 prime_attention 层的注意力权重张量，并选择在歌词键和音乐查询之间具有最佳线性对齐模式的 (layer, head)。</font></font><code>alignment_head</code><font style="vertical-align: inherit;"></font><code>small_single_enc_dec_prior</code><font style="vertical-align: inherit;"></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在采用新风格之前，对预先训练的顶层进行微调</font></font></h3><a id="user-content-fine-tune-pre-trained-top-level-prior-to-new-styles" class="anchor" aria-label="永久链接：在采用新风格之前，对预先训练的顶层进行微调" href="#fine-tune-pre-trained-top-level-prior-to-new-styles"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">之前，我们展示了如何从头开始训练小型顶层先验。假设您拥有至少 15 GB 内存且支持 fp16 的 GPU，您可以从我们预先训练的 1B 顶层先验进行微调。步骤如下：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"></font><code>--labels=True</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通过为您的数据集实施</font></font><code>get_metadata</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">提供</font><font style="vertical-align: inherit;">支持</font></font><code>jukebox/data/files_dataset.py</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 中添加新条目</font></font><code>jukebox/data/ids</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。我们建议用</font></font><code>"unknown"</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您选择的样式替换现有映射（例如重命名 等）。这使用预先训练的样式向量作为初始化，并可能节省一些计算。</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">完成这些修改后，运行</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,prior_1b_lyrics,all_fp16,cpu_ema --name=finetuned \
--sample_length=1048576 --bs=1 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=True --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mpiexec -n {ngpus} python jukebox/train.py --hps=vqvae,prior_1b_lyrics,all_fp16,cpu_ema --name=finetuned \
--sample_length=1048576 --bs=1 --aug_shift --aug_blend --audio_files_dir={audio_files_dir} \
--labels=True --train --test --prior --levels=3 --level=2 --weight_decay=0.01 --save_iters=1000" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为了获得最佳样本质量，建议最后对学习率进行退火。训练 5B 顶层需要 GPipe，但此版本不支持。</font></font></p>
<div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">引用</font></font></h1><a id="user-content-citation" class="anchor" aria-label="永久链接：引用" href="#citation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请使用以下 bibtex 条目引用：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>@article{dhariwal2020jukebox,
  title={Jukebox: A Generative Model for Music},
  author={Dhariwal, Prafulla and Jun, Heewoo and Payne, Christine and Kim, Jong Wook and Radford, Alec and Sutskever, Ilya},
  journal={arXiv preprint arXiv:2005.00341},
  year={2020}
}
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="@article{dhariwal2020jukebox,
  title={Jukebox: A Generative Model for Music},
  author={Dhariwal, Prafulla and Jun, Heewoo and Payne, Christine and Kim, Jong Wook and Radford, Alec and Sutskever, Ilya},
  journal={arXiv preprint arXiv:2005.00341},
  year={2020}
}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执照</font></font></h1><a id="user-content-license" class="anchor" aria-label="永久链接：许可证" href="#license"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><a href="/openai/jukebox/blob/master/LICENSE"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">非商业使用许可</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">它涵盖了已发布的代码和权重。</font></font></p>
</article></div>
