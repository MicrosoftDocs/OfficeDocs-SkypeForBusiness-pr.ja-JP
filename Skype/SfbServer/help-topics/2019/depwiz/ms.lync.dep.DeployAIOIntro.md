---
title: 単一の Standard Edition サーバーの準備 (開始)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 中央管理ストアとその他の配置されているサービスを選択することを保持するビジネス サーバーの Standard Edition サーバーは、Skype のインストールを開始するには、となるサーバー上のローカルの Administrators グループのメンバーとしてログインする必要があります。Standard Edition サーバーです。 [単一の Standard Edition サーバーの準備] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
ms.openlocfilehash: b4b211899ba907a20d11f8adf4d2640599dc6f91
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216586"
---
# <a name="prepare-single-standard-edition-server-intro"></a>単一の Standard Edition サーバーの準備 (開始)
 
中央管理ストアとその他の配置されているサービスを選択することを保持するビジネス サーバーの Standard Edition サーバーは、Skype のインストールを開始するには、となるサーバー上のローカルの Administrators グループのメンバーとしてログインする必要があります。Standard Edition サーバーです。 [**単一の Standard Edition サーバーの準備**] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
  
この特別なタスクは、Standard Edition サーバーをインフラストラクチャの最初のサーバーとして設定するように設計されています。 このタスクでは、Standard Edition サーバー上に SQL Server Express は、中央管理ストアをインストールします。 別の Standard Edition サーバーまたはフロントエンド プールを既に展開している場合は、[**キャンセル**] をクリックします。
  
> [!NOTE]
> このタスクを完了するは、(を既にインストールしていない) 場合は、トポロジ ビルダーをインストールし、トポロジ ドキュメントを構成します。 このトピックで説明するタスクを完了すると展開される中央管理ストアが利用できるようになるまで、トポロジ ドキュメントを公開することはできません。 
  

