require 'rake'

FOLDERS = %w(colors ftdetect ftplugin indent syntax doc plugin autoload)
SCRIPTS = %w(personal nerdtree vim-cucumber vim-rails vim-git vim-haml vim-scratch)
DOTVIM = "#{ENV['HOME']}/.vim"

desc "Install the files into ~/.vim"
task :install do
  FileUtils.mkdir_p FOLDERS.map{|f| "#{DOTVIM}/#{f}" }
  
  SCRIPTS.each do |s|
    FOLDERS.each do |f|
      FileUtils.cp Dir["#{s}/#{f}/*"], "#{DOTVIM}/#{f}"
    end
  end
end

desc "Remove everything in ~/.vim"
task :uninstall do
  FileUtils.rm_rf DOTVIM
end

desc "Blow everything out and try again."
task :reinstall => [:uninstall, :install]
