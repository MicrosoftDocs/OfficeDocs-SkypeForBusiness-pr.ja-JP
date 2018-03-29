---
title: Skype for Business Server 2015 で Config.xml を使用してインストール タスクを実行する
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Config.xml ファイルを使用して、追加のインストール手順の概要: 方法。'
ms.openlocfilehash: f55683d672df890be8baf0ac7ca50b3170faf3d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で Config.xml を使用してインストール タスクを実行する
 
**概要: ** Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。
  
Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。
  
- ネットワーク インストール ポイントのパスを指定する。
    
- インストールする製品を選択する。
    
- ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。
    
- インストール オプション (ユーザー名など) を指定する。
    
- Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。
    
- インストールに対する言語の追加または削除を行う。
    
Config.xml ファイルを使用して、Skype をビジネスのサイレント インストールを構成することをお勧めします。 
  
既定では、コア製品フォルダーに格納されている Config.xml ファイル (たとえば、\_製品_です。WW) では、その製品をインストールするように指示します。 などの次のフォルダーにある Config.xml ファイルには、ビジネスの Skype がインストールされます。
  
- \\server\share\Skype15\Skype.WW \Config.xml
    
ビジネスのインストールのため Skype を最もよく使用される Config.xml の要素は、次の表に表示されます。
  
**Config.xml の要素**

|**要素**|**説明**|
|:-----|:-----|
|Configuration  <br/> |最上位レベルの要素 (必須)。製品属性が含まれます。例: Product=Lync (Skype for Business クライアントで使用されます)  <br/> |
|OptionState  <br/> | インストール中、特定の製品の機能が処理される方法を指定します。 Outlook 2016 の妨げになる共有コンポーネントが含まれている Business Connectivity Services のインストールを防ぐために次の属性を使用します。 <br/>  Id ="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
|Display  <br/> | セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。 <br/>  CompletionNotice =「はい」 | 」No"(default) <br/>  AcceptEula =「はい」 | 」No"(default) <br/> |
|Logging  <br/> | セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。 <br/>  タイプ ="Off" | 」Standard"(default) | 「詳細」 <br/>  テンプレート ="_ファイル名_.txt」(ログ ファイルの名前)  <br/> |
|Setting  <br/> | Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。<br/>  Id の設定 ="_名前_"(Windows インストーラー プロパティの名前)  <br/>  値 ="_値_"(プロパティに代入する値)  <br/> |
|DistributionPoint  <br/> | インストールを実行するネットワーク インストール ポイントの完全修飾パス<br/>  場所 ="_パス_"  <br/> |
   
次の例では、ビジネスの Skype の標準的なサイレント インストールの Config.xml ファイルを示します。 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Office のインストールとメンテナンス タスクを実行するのには Config.xml ファイルの使用に関する詳細情報は[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)です。
  
## <a name="to-customize-the-configxml-file"></a>Config.xml ファイルをカスタマイズするには

1. Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。
    
2. 変更する要素を含む行に移動します。
    
3. 使用するサイレント オプションで要素のエントリを変更します。 コメント区切り記号を削除するかどうかを確認」\<!-"と"-\>」。 たとえば、次の構文を使用します。
    
  ```
  < DistributionPoint Location="\\server\share\Skype15" />
  ```

4. Config.xml ファイルを保存します。
    

