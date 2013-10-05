
---
# plenv

---
### 1. System PerlとLocal Perl 
LinuxやmacのOSには大抵の場合でSystem perlと呼ばれるものがデフォルトでインストールされています。  しかしこのSystem perlを使うのはオススメできません。  
OS内でSystem perlに依存してい動いているプログラムが存在するため、バージョンアップやカスタマイズした場合影響が出てしまいます。  

そこでplenvというツールを使ってLocal Perlをインストールするのが最近の手法となっています。

---
### 2. plenvとは
plenvとはPerlのバージョン管理ツールです。  

- コマンド一つでperl本体を簡単にインストールすることが可能です。
- 複数のバージョンのperlをインストールして使い分けることが可能です。
- root権限なしでperlをインストールすることが可能です。

---	
### 3. plenvのインストール
plenvを使用するためにはplenv自体のインストールとperl-buildのインストールが必要になります。  
  
・plenvのインストール  

	$ git clone git://github.com/tokuhirom/plenv.git ~/.plenv
	$ echo 'export PATH="$HOME/.plenv/bin:$PATH"' >> ~/.bash_profile
	$ echo 'eval "$(plenv init -)"' >> ~/.bash_profile
	$ exec $SHELL -l
・perl-buildのインストール

	$ git clone git://github.com/tokuhirom/Perl-Build.git ~/.plenv/plugins/perl-build/

---
### 4. plenvコマンド
plenvでよく使用するコマンドを紹介します。

・インストール可能なperl一覧

	$plenv install -l
	Available versions:
	 5.6.0
 	 5.6.1-TRIAL1
 	 5.6.1-TRIAL2
 	 5.6.1-TRIAL3
    	 (中略)
 	 5.17.10
 	 5.17.11
 	 5.18.0-RC1
 	 5.18.0-RC2
 	 5.18.0-RC3
 	 5.18.0-RC4
 	 5.18.0
 	 5.19.0

・perlのインストール

	$plenv install 5.16.3
	
・インストール済みのperl一覧

	$plenv versions  
	  system                                   
	* 5.16 (set by /Users/msys/.plenv/version) 
  	  5.16.3                                   
  	  5.18                                     
  	  5.8                                      
	
・使用するperlのバージョンを指定

	$plenv global 5.16.3
		=> 全体で使用するperlのバージョンを指定します。
	$plenv local 5.18.1
		=> 特定のディレクトリで使用するperlのバージョンを指定します。
		
・perlのアンインストール

	plenv uninstall 5.16.3
	
