---
title: ローカル構成ストアのインストールを起動 (設定)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 既にインストールされ構成されているセントラル サイトからトポロジ ビルダーを使用して発行する定義済みの構成を取得するとの間の中央管理ストアの読み取り専用のローカル コピーを保持するデータベースのインストールを開始するには、を選択します。管理ストア、またはその他のメディアから定義済みの構成を読み取り中です。 組織の内部ネットワーク上にあるマシンは、中央管理ストアから取得の構成を自動的に選択します。
ms.openlocfilehash: 87d2620b6b4b9eb36ee96e7f9b693016620d3a49
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003146"
---
# <a name="install-local-configuration-store-invoke-configure"></a>ローカル構成ストアのインストールを起動 (設定)
 
既にインストールされ構成されているセントラル サイトからトポロジ ビルダーを使用して発行する定義済みの構成を取得するとの間の中央管理ストアの読み取り専用のローカル コピーを保持するデータベースのインストールを開始するには、を選択します。管理ストア、またはその他のメディアから定義済みの構成を読み取り中です。 組織の内部ネットワーク上にあるコンピューターでは、**中央管理ストアから自動的に構成を取得する**を選択します。
  
エッジ サーバーを中央管理ストアのレプリカをインストールする場合は、USB フラッシュ ドライブ、USB ハード ディスク ドライブ、CD-ROM、またはその他のメディアなどのポータブル メディアからエクスポートされた構成の文書のコピーを読み取りが選択します。 
  
> [!IMPORTANT]
> エッジ サーバーのローカル構成ストアをインストールする場合の構成については、必要があるサーバーの全体管理からエクスポートされた形式で保存 Windows PowerShell コマンドレットを実行しています。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
適切なオプションを選択した後は、**次へ**をクリックします。
  

