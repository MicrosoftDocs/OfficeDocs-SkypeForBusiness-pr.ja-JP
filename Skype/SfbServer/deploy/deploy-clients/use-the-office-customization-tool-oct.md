---
title: '[カスタム カスタマイズ Officeツール (OCT) を使用Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: カスタム カスタマイズ ツールを Officeクライアントで使用するSkype for Businessします。'
ms.openlocfilehash: 435ce2e1b9644fe5f30968a0766abe69165ca387
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738953"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>[カスタム カスタマイズ Officeツール (OCT) を使用Skype for Business Server
 
**概要:** クライアントと一緒Officeカスタマイズ ツールを使用Skype for Business方法。
  
カスタム Office (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズに推奨されるツールです。 OCT を使用して、セットアップ Office .msp ファイルにカスタマイズを保存します。 ネットワーク インストール ポイントの [更新プログラム] フォルダーにファイルを配置します。 このファイルをOfficeセットアップは、[更新] フォルダーでセットアップ カスタマイズ ファイルを検索し、カスタマイズを適用します。 Updates フォルダーは、ソフトウェア更新プログラムを初期インストール時に展開する場合にのみ使用Office。
  
OCT はセットアップの一部であり、ボリューム ライセンスバージョンの製品にのみ使用されます。 OCT を実行するには、ソース ファイルを含むネットワーク インストール ポイントのルートからコマンド ライン `setup.exe /admin` Officeします。 たとえば、次の値を使用します。
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理者は OCT を使用してセットアップ カスタマイズ .msp ファイルを作成し、次の領域をカスタマイズできます。
  
- **セットアップ** クライアントと既定の組織名、追加のネットワーク インストール ソース、プロダクト キー、エンド ユーザー ライセンス契約、表示レベル、削除する以前のバージョンの Office、インストール中に実行するカスタム プログラム、セキュリティ設定、セットアップ プロパティを指定するために使用されます。
    
- **機能** ユーザー設定の構成および機能のインストール方法Office使用します。 管理者は OCT を使用して、ユーザーのアプリケーション設定Office既定値を指定できます。 ユーザーはインストール後に大部分の設定を変更できます。
    
- **その他のコンテンツ** ファイルの追加または削除、レジストリ エントリの追加または削除、ショートカットの構成に使用されます。
    
- **Outlook** ユーザーの既定のプロファイルプロファイルをカスタマイズOutlook、Exchange設定の指定、アカウントの追加、アカウントの削除とエクスポート設定、および Send\Receive グループの指定を行います。
    
OCT の詳細については、「Use [the OCT to customize the OCT to customize the OCT 2013」](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))をOfficeしてください。 この情報は、以降のバージョンのアプリケーションにも適用Office。
