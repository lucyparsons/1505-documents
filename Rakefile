pdf_files = Rake::FileList.new "**/*.pdf"
text_files = pdf_files.sub '.pdf', '.txt'
task :default => text_files

rule '.txt' => '.tiff' do |t|
  sh "tesseract \"#{t.source}\" \"#{t.name.sub '.txt', ''}\""
end

rule '.tiff' => '.pdf' do |t|
  sh "convert -density 300 -alpha Off -depth 8 \"#{t.source}\" \"#{t.name}\""
end
