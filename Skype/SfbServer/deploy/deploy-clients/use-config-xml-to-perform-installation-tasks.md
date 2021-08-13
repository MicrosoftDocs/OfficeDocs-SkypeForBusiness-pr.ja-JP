---
title: クライアントConfig.xmlインストール タスクを実行するには、Skype for Business使用します。
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
ms.openlocfilehash: b7c04a9c08f6a5dd51c21a189ce3a07d81a589cf694e5020a75cf6f646bd1cef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332049"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>クライアントConfig.xmlインストール タスクを実行するには、Skype for Business使用します。

**概要:** 追加のインストール手順を指定Config.xmlファイルを使用する方法。

Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。

- ネットワーク インストール ポイントのパスを指定する。

- インストールする製品を選択する。

- ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。

- インストール オプション (ユーザー名など) を指定する。

- Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。

- インストールに対して言語の追加または削除を行う。

サイレント インストールを構成するには、Config.xmlファイルをSkype for Businessすることをお勧めします。 

既定では、コアConfig.xmlに格納されているファイル (\製品など) を指定 _します_。WW) は、セットアップを指示して、その製品をインストールします。 たとえば、次のフォルダーConfig.xmlファイルがインストールされますSkype for Business。

- \\server\share\Skype15\Skype。WW \Config.xml

インストールConfig.xml最も一般的に使用されるSkype for Business次の表に示します。

**Config.xml の要素**


| **Element**              | **説明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 構成  <br/>     | トップ レベルの要素 (必須)。 Product=Lync など、Product 属性が含まれている (これは、クライアントのSkype for Businessします)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | インストール中、特定の製品の機能が処理される方法を指定します。 次の属性を使用して、Business Connectivityサービスのインストールを防止します。この属性には、Outlook。 <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| ディスプレイ  <br/>           | セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。 <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| ログ記録  <br/>           | セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。 <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。<br/>  Id="*の名前を設定* する (インストーラー プロパティのWindows)  <br/>  Value=" *値*" (プロパティに割り当てる値)  <br/>                                                             |
| DistributionPoint  <br/> | インストールを実行するネットワーク インストール ポイントの完全修飾パス<br/>  Location=" *パス*"  <br/>                                                                                                                                     |

次の使用例は、Config.xmlクライアントの一般的なサイレント インストール用のSkype for Businessします。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

インストールおよび保守タスクの実行に Config.xmlファイルを使用Office詳細については、以下を参照してください [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 。

## <a name="to-customize-the-configxml-file"></a>Config.xml ファイルをカスタマイズするには

1. Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。

2. 変更する要素を含む行に移動します。

3. 使用するサイレント オプションで要素のエントリを変更します。 コメント区切り記号 "" を削除してください \<!--" and "--\> 。 たとえば、次の構文を使用します。

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml ファイルを保存します。