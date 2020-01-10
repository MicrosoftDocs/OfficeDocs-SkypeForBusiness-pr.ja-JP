---
title: Skype for Business Server で Office カスタマイズツール (OCT) を使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: '概要: Skype for Business クライアントで Office カスタマイズツールを使用する方法について説明します。'
ms.openlocfilehash: b5c66fee4f6c879c8ded2897b64e63654dd950be
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001597"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Skype for Business Server で Office カスタマイズツール (OCT) を使用する
 
**概要:** Skype for Business クライアントで Office カスタマイズツールを使用する方法について説明します。
  
Office カスタマイズ ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズにおける推奨ツールになっています。 OCT を使用して Office をカスタマイズし、カスタマイズ内容をセットアップ カスタマイズ (.msp) ファイルに保存します。 そのファイルをネットワーク インストール ポイントの Updates フォルダーに配置します。 Office をインストールするときに、セットアップは Updates フォルダーのセットアップ カスタマイズ ファイルを検索し、カスタマイズ内容を適用します。 Updates フォルダーは、Office の最初のインストール中にソフトウェアの更新プログラムを展開するためにのみ使用できます。
  
OCT はセットアップの一部であり、ボリュームライセンス版の製品でのみ使用されます。 Office のソースファイルが含ま`setup.exe /admin`れているネットワークインストールポイントのルートからコマンドラインを入力して、OCT を実行します。 たとえば、次のようなコマンドを使用します。
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理者は、OCT を使用して、セットアップカスタマイズの .msp ファイルを作成し、次の領域をカスタマイズすることができます。
  
- **セットアップ**クライアントと既定の組織名、追加のネットワークインストールソース、プロダクトキー、エンドユーザーライセンス契約、表示レベル、以前のバージョンの Office を削除するためのカスタムプログラム、インストール時、セキュリティ設定、セットアップのプロパティなど、既定のインストール場所を指定するために使用されます。
    
- **機能**ユーザー設定を構成し、Office 機能のインストール方法をカスタマイズするために使用されます。 管理者は、OCT を使用して、ユーザーの Office アプリケーション設定の初期既定値を指定することができます。 ユーザーはインストール後にほとんどの設定を変更できます。
    
- **追加コンテンツ**ファイルを追加または削除したり、レジストリエントリを追加または削除したり、ショートカットを構成したりするために使用されます。
    
- **Outlook**ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート、Send\Receive グループの指定を行うために使用されます。
    
OCT の詳細については、「 [oct を使用して Office 2013 をカスタマイズする](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))」を参照してください。 この情報は、新しいバージョンの Office にも適用されることに注意してください。
  

