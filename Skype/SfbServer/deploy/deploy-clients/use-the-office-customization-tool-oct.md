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
description: '概要: Skype for Business クライアントで Office カスタマイズ ツールを使用する方法について説明します。'
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812567"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Skype for Business Server Officeカスタマイズ ツール (OCT) を使用する
 
**概要:** Skype for Business クライアントで Office カスタマイズ ツールを使用する方法。
  
Office ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズに推奨されるツールです。 OCT を使用して、カスタマイズOfficeセットアップ カスタマイズ .msp ファイルに保存します。 ネットワーク インストール ポイントの Updates フォルダーにファイルを配置します。 このファイルをOfficeセットアップは Updates フォルダーでセットアップ カスタマイズ ファイルを検索し、カスタマイズを適用します。 Updates フォルダーは、更新プログラムの初期インストール時にソフトウェア更新プログラムを展開する場合にのみOffice。
  
OCT はセットアップの一部であり、ボリューム ライセンスバージョンの製品にのみ使用されます。 OCT を実行するには、ソース ファイルに含まれるネットワーク インストール ポイントのルートからコマンド ラインOffice  `setup.exe /admin` 入力します。 たとえば、次の値を使用します。
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理者は OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズできます。
  
- **セットアップ** クライアントの既定のインストール場所と既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、エンドユーザー 使用許諾契約書、表示レベル、削除する以前のバージョンの Office、インストール中に実行するカスタム プログラム、セキュリティ設定、およびセットアップ プロパティを指定するために使用されます。
    
- **機能** ユーザー設定を構成し、機能のインストールOfficeカスタマイズするために使用します。 管理者は OCT を使用して、ユーザーのアプリケーション設定にOffice既定値を指定できます。 ユーザーはインストール後に大部分の設定を変更できます。
    
- **その他のコンテンツ** ファイルの追加または削除、レジストリ エントリの追加または削除、およびショートカットの構成に使用します。
    
- **Outlook** ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート、および送受信グループの指定に使用されます。
    
OCT の詳細については、「OCT を使用してユーザー設定をカスタマイズ[する」をOffice 2013。](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) この情報は、新しいバージョンのファイルにも適用Office。
  

