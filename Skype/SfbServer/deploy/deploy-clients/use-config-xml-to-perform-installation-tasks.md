---
title: Skype for Business クライアントで Config.xml を使ってインストールタスクを実行する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '概要:  Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。'
ms.openlocfilehash: d561e4f6e3213ae7dff160b9b43e02f26ecc0522
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002937"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Skype for Business クライアントで Config.xml を使ってインストールタスクを実行する

**概要: ** Config.xml ファイルを使用して追加のインストール手順を指定する方法について説明します。

Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。

- ネットワーク インストール ポイントのパスを指定する。

- インストールする製品を選択する。

- ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。

- インストール オプション (ユーザー名など) を指定する。

- Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。

- インストールに対する言語の追加または削除を行う。

Config.xml ファイルを使用して、Skype for Business のサイレントインストールを構成することをお勧めします。 

既定では、コア製品フォルダーに保存されている Config.xml ファイル (たとえば、\ _product_)。WW) その製品をインストールするようにセットアップに指示します。 たとえば、次のフォルダーの Config.xml ファイルは、Skype for Business をインストールします。

- \\skype \ Skype15\ Skype\Config.xml

Skype for Business をインストールするために最もよく使われる Config.xml 要素は、次の表に記載されています。

**Config.xml の要素**


| **要素**              | **説明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration  <br/>     | 最上位レベルの要素 (必須)。製品属性が含まれます。例: Product=Lync (Skype for Business クライアントで使用されます)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | インストール中、特定の製品の機能が処理される方法を指定します。 次の属性を使用して、Business Connectivity Services のインストールを防止します。これには、Outlook を妨害する共有コンポーネントが含まれます。 <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Display  <br/>           | セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。 <br/>  補完の通知 = "はい"                                                                                                                                                                                |
| Logging  <br/>           | セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。 <br/>  「= "オフ"」と入力します。                                                                                                                                                                                       |
| Setting  <br/>           | Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。<br/>  設定 Id = " *name*" (Windows Installer プロパティの名前)  <br/>  値 = "*値*" (プロパティに割り当てる値)  <br/>                                                             |
| DistributionPoint  <br/> | インストールを実行するネットワーク インストール ポイントの完全修飾パス<br/>  Location = " *path*"  <br/>                                                                                                                                     |

次の例は、Skype for Business クライアントの一般的なサイレントインストール用の Config.xml ファイルを示しています。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Config.xml ファイルを使用して Office のインストールとメンテナンスタスクを実行する方法について[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)詳しくは、を参照してください。

## <a name="to-customize-the-configxml-file"></a>Config.xml ファイルをカスタマイズするには

1. Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。

2. 変更する要素を含む行に移動します。

3. 使用するサイレント オプションで要素のエントリを変更します。 コメントの区切り文字 "\<!--" と "--\>" は削除してください。 たとえば、次の構文を使用します。

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml ファイルを保存します。


