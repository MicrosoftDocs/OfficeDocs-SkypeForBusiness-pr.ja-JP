---
title: 単一の Standard Edition サーバーの準備 (開始)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 中央管理ストアとその他の併置されたサービスを保持する Skype for Business Server Standard Edition Server のインストールを開始するには、対象となるサーバーのローカル管理者グループのメンバーとしてログインしている必要があります。Standard Edition サーバー。 [単一の Standard Edition サーバーの準備] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
ms.openlocfilehash: 437f90fa99efa920479e7c0dc966c3c63fd5eed1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796978"
---
# <a name="prepare-single-standard-edition-server-intro"></a>単一の Standard Edition サーバーの準備 (開始)
 
中央管理ストアとその他の併置されたサービスを保持する Skype for Business Server Standard Edition Server のインストールを開始するには、対象となるサーバーのローカル管理者グループのメンバーとしてログインしている必要があります。Standard Edition サーバー。 [**単一の Standard Edition サーバーの準備**] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
  
この特別なタスクは、Standard Edition サーバーをインフラストラクチャの最初のサーバーとして設定するように設計されています。 このタスクは、SQL Server Express の中央管理ストアを Standard Edition Server にインストールします。 別の Standard Edition サーバーまたはフロントエンド プールを既に展開している場合は、[**キャンセル**] をクリックします。
  
> [!NOTE]
> このタスクが完了したら、トポロジビルダーをインストールし (まだインストールしていない場合)、トポロジドキュメントを構成します。 このトピックで説明するタスクを完了すると展開される中央管理ストアが利用できるようになるまで、トポロジ ドキュメントを公開することはできません。 
  

