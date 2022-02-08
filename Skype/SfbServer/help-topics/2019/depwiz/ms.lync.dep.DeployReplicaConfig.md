---
title: ローカル構成ストアのインストールの起動 (構成)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 中央管理ストアのローカル読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールおよび構成されているサーバーの全体管理ストアからトポロジ ビルダーを使用して発行された定義済みの構成を取得するか、他のメディアから定義された構成を読み取るのを選択します。 組織の内部ネットワーク上にあるコンピューターの場合は、[サーバーの全体管理ストアから構成を自動的に取得する] を選択します。
ms.openlocfilehash: b450a4a76dd7b43065e2784ba6f0cef9f18a1b6e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390599"
---
# <a name="install-local-configuration-store-invoke-configure"></a>ローカル構成ストアの起動のインストール (構成)
 
中央管理ストアのローカル読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールおよび構成されているサーバーの全体管理ストアからトポロジ ビルダーを使用して発行された定義済みの構成を取得するか、他のメディアから定義された構成を読み取るのを選択します。 組織の内部ネットワーク上にあるコンピューターの場合は、[サーバーの全体管理ストアから構成を自動的に取得 **する] を選択します**。
  
エッジ サーバーに中央管理ストアのレプリカをインストールする場合は、USB フラッシュ ドライブ、USB ハード ディスク ドライブ、または CD-ROM その他のポータブル メディアから、構成ドキュメントのエクスポート コピーを読み取る方法を選択します。 
  
> [!IMPORTANT]
> エッジ サーバーにローカル構成ストアをインストールする場合、構成情報は、Windows PowerShell コマンドレットを実行してサーバーの全体管理ストアからエクスポートされた形式である必要があります。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
適切なオプションを選択したら、**[次へ]** をクリックします。
  

