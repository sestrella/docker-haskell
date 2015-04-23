def with_dockerfiles(&block)
  Dir.glob('*/Dockerfile') do |f|
    yield f
  end
end

task :build_all do
  with_dockerfiles do |f|
    tag = File.dirname f
    Dir.chdir(tag) do
      sh "docker build --force-rm -t sestrella/haskell:#{tag} ."
    end
  end
end

task :echo_versions do
  with_dockerfiles do |f|
    tag = File.dirname f
    Dir.chdir(tag) do
      puts "\nUsing image: sestrella/haskell:#{tag}"
      sh "docker run --rm sestrella/haskell:#{tag} ghc --version"
      sh "docker run --rm sestrella/haskell:#{tag} cabal --version"
    end
  end
end
