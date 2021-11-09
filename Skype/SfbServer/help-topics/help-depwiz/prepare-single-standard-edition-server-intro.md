---
title: 単一の Standard Edition サーバーの準備 (開始)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 選択したサーバーの全体管理ストアと他の接続されたサービスを保持する Skype for Business Server 2015 Standard Edition サーバーのインストールを開始するには、Standard Edition サーバーになるサーバー上のローカル Administrators グループのメンバーとしてログインする必要があります。 [単一の Standard Edition サーバーの準備] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
ms.openlocfilehash: 58c25ce952cb888f4595af2b67395b4d764edc5d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850150"
---
# <a name="prepare-single-standard-edition-server-intro"></a>単一の Standard Edition サーバーの準備 (開始)
 
選択したサーバーの全体管理ストアと他の接続されたサービスを保持する Skype for Business Server 2015 Standard Edition サーバーのインストールを開始するには、Standard Edition サーバーになるサーバー上のローカル Administrators グループのメンバーとしてログインする必要があります。 **[単一の Standard Edition サーバーの準備]** ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
  
この特別なタスクは、Standard Edition サーバーをインフラストラクチャの最初のサーバーとして設定するよう設計されています。 このタスクでは、サーバーの全体管理ストア (SQL Server ExpressサーバーにStandard Editionします。 別の Standard Edition サーバーまたはフロントエンド プールを既に展開している場合は、**[キャンセル]** をクリックします。
  
> [!NOTE]
> このタスクが完了したら、トポロジ ビルダー (まだインストールしていない場合) をインストールし、トポロジ ドキュメントを構成します。 このトピックで説明するタスクを完了すると展開される中央管理ストアが利用できるようになるまで、トポロジ ドキュメントを公開することはできません。 
  

