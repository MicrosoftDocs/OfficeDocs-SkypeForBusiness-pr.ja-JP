---
title: ローカル構成ストアのインストールの起動 (構成)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 中央管理ストアのローカルの読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールされている構成済みのセントラルで、トポロジビルダーを使用して発行された定義済みの構成を取得するように選択します。管理ストア、または他のメディアから定義された構成を読み取ります。 組織の内部ネットワーク上にあるコンピューターの場合は、[セントラル管理ストアから自動的に構成を取得する] を選択します。
ms.openlocfilehash: a689d8cd7926cca109b808f8a186396dd48caaf8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705302"
---
# <a name="install-local-configuration-store-invoke-configure"></a>ローカル構成ストアのインストールの起動 (構成)
 
中央管理ストアのローカルの読み取り専用コピーを保持するデータベースのインストールを開始するには、既にインストールされている構成済みのセントラルで、トポロジビルダーを使用して発行された定義済みの構成を取得するように選択します。管理ストア、または他のメディアから定義された構成を読み取ります。 組織の内部ネットワーク上にあるコンピューターの場合は、[**セントラル管理ストアから自動的に構成を取得**する] を選択します。
  
エッジサーバーに中央管理ストアの複製をインストールする場合は、USB フラッシュドライブ、USB ハードディスクドライブ、CD-ROM などのメディアから、エクスポートした構成ドキュメントのコピーをポータブルメディアから読み取ることを選択します。 
  
> [!IMPORTANT]
> エッジサーバーにローカル構成ストアをインストールする場合、構成情報は、Windows PowerShell コマンドレットを実行して、中央管理ストアからエクスポートした形式である必要があります。`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
適切なオプションを選んだら、[**次へ**] をクリックします。
  

