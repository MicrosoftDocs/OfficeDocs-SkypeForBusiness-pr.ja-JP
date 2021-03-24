---
title: Skype for Business Server Officeカスタマイズ ツール (OCT) を使用する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: Skype for Business クライアントOfficeカスタマイズ ツールを使用する方法について説明します。'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100453"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Skype for Business Server Officeカスタマイズ ツール (OCT) を使用する
 
**概要:** Skype for Business クライアントOfficeカスタマイズ ツールを使用する方法。
  
カスタム Office (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズに推奨されるツールです。 OCT を使用して、ユーザー設定Officeカスタマイズをセットアップ カスタマイズ .msp ファイルに保存します。 ネットワーク インストール ポイントの [更新プログラム] フォルダーにファイルを配置します。 このファイルをインストールOfficeセットアップは、[更新プログラム] フォルダーでセットアップ カスタマイズ ファイルを検索し、カスタマイズを適用します。 Updates フォルダーは、ソフトウェア更新プログラムを初期インストール時に展開する場合にのみ使用Office。
  
OCT はセットアップの一部であり、ボリューム ライセンスバージョンの製品にのみ使用されます。 OCT を実行するには、ソース ファイルを含むネットワーク インストール ポイントのルートからコマンド ライン  `setup.exe /admin` Officeします。 たとえば、次の値を使用します。
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理者は OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズできます。
  
- **セットアップ** クライアントと既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、エンド ユーザー ライセンス契約、表示レベル、削除する以前のバージョンの Office、インストール中に実行するカスタム プログラム、セキュリティ設定、セットアップ プロパティを指定するために使用します。
    
- **機能** ユーザー設定の構成および機能のインストール方法Office使用します。 管理者は OCT を使用して、ユーザーのアプリケーション設定Office既定の値を指定できます。 ユーザーはインストール後に大部分の設定を変更できます。
    
- **その他のコンテンツ** ファイルの追加または削除、レジストリ エントリの追加または削除、ショートカットの構成に使用されます。
    
- **Outlook** ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除、設定のエクスポート、および Send\Receive グループの指定に使用されます。
    
OCT の詳細については、「OCT を使用してユーザー設定を[カスタマイズする」をOffice 2013。](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) この情報は、以降のバージョンにも適用Office。
