---
title: Skype for Business Config.xmlインストール タスクを実行するには、このコマンドを使用します。
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
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825187"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Skype for Business Config.xmlを使用してインストール タスクを実行する

**概要:** このファイルを使用してConfig.xml手順を指定する方法について説明します。

Office カスタマイズ ツール (OCT) はカスタマイズ インストール向けの主要ツールですが、管理者は OCT では使用できない追加のインストール手順を Config.xml ファイルによって指定できます。以下のカスタマイズは、Config.xml ファイルを使用しないと実行できません。

- ネットワーク インストール ポイントのパスを指定する。

- インストールする製品を選択する。

- ログ記録や、セットアップ カスタマイズ ファイルおよびソフトウェア更新プログラムの場所を構成する。

- インストール オプション (ユーザー名など) を指定する。

- Office をインストールせずにローカル インストール ソース (LIS) をユーザーのコンピューターにコピーする。

- インストールに対して言語の追加または削除を行う。

Skype for Business のサイレント インストールを構成Config.xmlファイルを使用することをお勧めします。 

既定では、コアConfig.xmlフォルダーに格納されているファイル (\ product など) を指定 _します_。WW) は、セットアップに製品のインストールを指示します。 たとえば、次のフォルダーConfig.xmlファイルは Skype for Business をインストールします。

- \\server\share\Skype15\Skype.WW \Config.xml

次Config.xml Skype for Business のインストールで最も一般的に使用される次の要素の一覧を示します。

**Config.xml の要素**


| **要素**              | **説明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 構成  <br/>     | トップ レベルの要素 (必須)。 Product 属性を含む。例: Product=Lync (これは Skype for Business クライアントで機能します)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | インストール中、特定の製品の機能が処理される方法を指定します。 Outlook に干渉する共有コンポーネントを含むBusiness Connectivity Servicesをインストールしないようにするには、次の属性を使用します。 <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| ディスプレイ  <br/>           | セットアップがユーザーに表示する UI のレベル。一般的には次の属性があります。 <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| ログ記録  <br/>           | セットアップが実行するログ記録の種類のオプション。一般的には次の属性があります。 <br/>  Type ="Off"                                                                                                                                                                                       |
| Setting  <br/>           | Windows インストーラーのプロパティの値を指定します。一般的には次の属性があります。<br/>  Setting Id=" *name*" (Windows インストーラー プロパティの名前)  <br/>  Value=" *値*" (プロパティに割り当てる値)  <br/>                                                             |
| DistributionPoint  <br/> | インストールを実行するネットワーク インストール ポイントの完全修飾パス<br/>  Location=" *path*"  <br/>                                                                                                                                     |

次の例は、Config.xml Skype for Business クライアントの一般的なサイレント インストールのファイルを示しています。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Config.xml ファイルを使用してインストールとOfficeタスクを実行する方法の詳細については、以下を参照してください [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) 。

## <a name="to-customize-the-configxml-file"></a>Config.xml ファイルをカスタマイズするには

1. Notepad などのテキスト エディター ツールで Config.xml ファイルを開きます。

2. 変更する要素を含む行に移動します。

3. 使用するサイレント オプションで要素のエントリを変更します。 コメント区切り記号 " " を必ず削除してください \<!--" and "--\> 。 たとえば、次の構文を使用します。

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Config.xml ファイルを保存します。


