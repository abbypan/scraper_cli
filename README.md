# scraper_cli
use perl Web::Scraper to extract webpage data on simple command line

简单命令行调用perl的Web::Scraper取网页数据

## example

read from : url , html file, stdin url string, stdin html content

读入url，html文件，或标准输入指定的url、html内容

```bash
scraper_cli.pl -i http://www.google.com -p "//a" -r "TEXT"
scraper_cli.pl -i google.html -p "//a" -r "TEXT"
echo "http://www.google.com" | scraper_cli.pl -p "//a" -r "TEXT"
cat "google.html" | scraper_cli.pl -p "//a" -r "TEXT"
```

extract data : single data like TEXT/HTML/@attr => plain text, multi data => json text

单个元素提取直接写入普通文本文件，多个元素提取则写入json文本文件

```bash
scraper_cli.pl -i http://www.google.com -p "//a" -r "TEXT"
scraper_cli.pl -i http://www.google.com -p "//a" -r "HTML"
scraper_cli.pl -i http://www.google.com -p "//a" -r "@href"
scraper_cli.pl -i http://www.google.com -p "//a" -r " id=> '@href', text => 'TEXT' "
```

## args

    -i url or input html file; otherwise, use stdin
    -p xpath string
    -c charset
    -r return data, for example, HTML / TEXT / \@href
    -f process or process_first
    -o extract data write to file; otherwise, use stdout
    -h help

## install 
```
cpan App::cpanminus
cpanm Encode::Locale JSON LWP::UserAgent Web::Scraper
```
