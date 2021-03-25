---
title: Skype for business Config.xmlでインストール タスクを実行するには、次の手順を実行します。
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: '概要: Config.xmlファイルを使用して、追加のインストール手順を指定する方法について説明します。'
ms.openlocfilehash: dbf4c4ba4e652f4b777e0c901fee4ffb0ad68af3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121141"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Skype for business Config.xmlでインストール タスクを実行するには、次の手順を実行します。

**概要:** 追加のインストール手順を指定Config.xmlファイルを使用する方法。

Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。

- ネットワーク インストール ポイントのパスを指定する。

- インストールする製品を選択する。

- ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。

- インストール オプション (ユーザー名など) を指定する。

- Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。

- インストールに対して言語の追加または削除を行う。

Skype for Business サイレント インストールを構成するには、Config.xmlファイルを使用することをお勧めします。 

既定では、コアConfig.xmlに格納されているファイル (\製品など) を指定 _します_。WW) は、セットアップを指示して、その製品をインストールします。 たとえば、次のフォルダーConfig.xmlファイルは Skype for Business をインストールします。

- \\server\share\Skype15\Skype.WW \Config.xml

Skype for Business Config.xml最も一般的に使用される要素の一覧を次の表に示します。

**Config.xml の要素**


| **要素**              | **説明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 構成  <br/>     | トップ レベルの要素 (必須)。 Product 属性 (Product=Lync など) が含まれる (これは Skype for Business クライアントで機能します)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | インストール中、特定の製品の機能が処理される方法を指定します。 Outlook に干渉する共有コンポーネントを含むBusiness Connectivity Servicesのインストールを防止するには、次の属性を使用します。 <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| ディスプレイ  <br/>           | セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。 <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| ログ記録  <br/>           | セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。 <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。<br/>  Id=" *という名前を設定* する (Windows インストーラー プロパティの名前)  <br/>  Value=" *値*" (プロパティに割り当てる値)  <br/>                                                             |
| DistributionPoint  <br/> | インストールを実行するネットワーク インストール ポイントの完全修飾パス<br/>  Location=" *パス*"  <br/>                                                                                                                                     |

次の使用例は、skype for Business クライアントConfig.xmlサイレント インストールの一般的なファイルを示しています。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Config.xmlファイルを使用してインストールおよびOfficeタスクを実行する方法の詳細については、以下のページを参照してください [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 。

## <a name="to-customize-the-configxml-file"></a>Config.xml ファイルをカスタマイズするには

1. Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。

2. 変更する要素を含む行に移動します。

3. 使用するサイレント オプションで要素のエントリを変更します。 コメント区切り記号 "" を削除してください \<!--" and "--\> 。 たとえば、次の構文を使用します。

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml ファイルを保存します。