---
title: Skype で、Office カスタマイズ ツール (OCT) を使用して、ビジネスのサーバーの
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: Skype で、Office カスタマイズ ツールを使用して、クライアントのビジネスの方法です。'
ms.openlocfilehash: 6530199ce86914feae6b44ae8b73137263fcd6a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883582"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Skype で、Office カスタマイズ ツール (OCT) を使用して、ビジネスのサーバーの
 
**の概要:** ビジネス クライアントに、Skype で、Office カスタマイズ ツールを使用する方法です。
  
Office カスタマイズ ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズにおける推奨ツールになっています。 OCT を使用して Office をカスタマイズし、カスタマイズ内容をセットアップ カスタマイズ (.msp) ファイルに保存します。 そのファイルをネットワーク インストール ポイントの Updates フォルダーに配置します。 Office をインストールするときに、セットアップは Updates フォルダーのセットアップ カスタマイズ ファイルを検索し、カスタマイズ内容を適用します。 Updates フォルダーは、Office の初回インストール時にソフトウェア更新プログラムの展開にのみ使用できます。
  
OCT は、セットアップの一部とは、ボリューム ライセンスを購入のバージョンの製品にのみ使用します。 入力して OCT を実行する`setup.exe /admin`、Office を含むネットワーク インストール ポイントのルートからコマンド ・ ラインでは、ソース ファイルです。 たとえば、次のようなコマンドを使用します。
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
管理者は、OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズすることができます。
  
- **セットアップ**レベルは、以前、時に実行するカスタム プログラムを削除する Office のバージョンを表示するクライアントと既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、使用許諾契約書の既定のインストール場所を指定するために使用、インストール、セキュリティ設定、およびセットアップ プロパティです。
    
- **機能**ユーザー設定を構成して、Office 機能のインストール方法をカスタマイズするのにを使用します。 管理者は、OCT を使用してユーザーの Office アプリケーションの設定の既定の初期値を指定します。 ユーザーは、インストール後、ほとんどの設定を変更できます。
    
- **その他のコンテンツ**追加またはファイルを削除するために使用とを追加またはレジストリ エントリを削除し、ショートカットを構成します。
    
- **Outlook**使用すると、ユーザーの既定の Outlook プロファイルをカスタマイズするのには、Exchange 設定の指定、アカウントを追加、アカウントを削除しての設定をエクスポートおよび送受信グループを指定します。
    
OCT の詳細についてを参照してください[OCT を使用して Office 2013 をカスタマイズするのには](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))です。 この情報が Office の新しいバージョンにも適用されることに注意してください。
  

