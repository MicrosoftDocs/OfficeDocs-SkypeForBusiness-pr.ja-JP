---
title: Config.xml を使用して、Skype のビジネスのクライアントのインストール ・ タスクを実行するのには
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '概要:  Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。'
ms.openlocfilehash: a6234424240dc0d7ebb70762598467bfcee997e2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371514"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Config.xml を使用して、Skype のビジネスのクライアントのインストール ・ タスクを実行するのには

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


| **要素**              | **説明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration  <br/>     | 最上位レベルの要素 (必須)。製品属性が含まれます。例: Product=Lync (Skype for Business クライアントで使用されます)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | インストール中、特定の製品の機能が処理される方法を指定します。 干渉する Outlook の共有コンポーネントが含まれている Business Connectivity Services のインストールを防ぐために次の属性を使用します。 <br/>  Id ="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Display  <br/>           | セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。 <br/>  CompletionNotice =「はい」                                                                                                                                                                                |
| Logging  <br/>           | セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。 <br/>  タイプ ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。<br/>  Id の設定 ="*名前*"(Windows インストーラー プロパティの名前)  <br/>  値 ="*値*"(プロパティに代入する値)  <br/>                                                             |
| DistributionPoint  <br/> | インストールを実行するネットワーク インストール ポイントの完全修飾パス<br/>  場所 ="*パス*"  <br/>                                                                                                                                     |

ビジネス クライアント用の Skype の場合は、標準的なサイレント インストール用の Config.xml ファイルを次の例に示します。 

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

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml ファイルを保存します。


