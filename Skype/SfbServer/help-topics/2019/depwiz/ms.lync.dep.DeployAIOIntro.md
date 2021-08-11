---
title: 単一の Standard Edition サーバーの準備 (開始)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 選択したサーバーの全体管理ストアと他の接続されたサービスを保持する Skype for Business Server Standard Edition サーバーのインストールを開始するには、Standard Edition サーバーになるサーバー上のローカル Administrators グループのメンバーとしてログインする必要があります。 [単一の Standard Edition サーバーの準備] ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
ms.openlocfilehash: 352b4ece936d609ed73540370313d21e83b9034c5efdbbdefb40528921bf8e34
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292245"
---
# <a name="prepare-single-standard-edition-server-intro"></a>単一の Standard Edition サーバーの準備 (開始)
 
選択したサーバーの全体管理ストアと他の接続されたサービスを保持する Skype for Business Server Standard Edition サーバーのインストールを開始するには、Standard Edition サーバーになるサーバー上のローカル Administrators グループのメンバーとしてログインする必要があります。 **[単一の Standard Edition サーバーの準備]** ページに、初期インストールの要件が表示されます。 コンピューターが展開先のドメインのメンバーであり、フォレストでスキーマ、フォレスト、およびドメインの準備を正常に完了している必要があります。
  
この特別なタスクは、Standard Edition サーバーをインフラストラクチャの最初のサーバーとして設定するよう設計されています。 このタスクでは、サーバーの全体管理ストア (SQL Server ExpressサーバーにStandard Editionします。 別の Standard Edition サーバーまたはフロントエンド プールを既に展開している場合は、**[キャンセル]** をクリックします。
  
> [!NOTE]
> このタスクが完了したら、トポロジ ビルダー (まだインストールしていない場合) をインストールし、トポロジ ドキュメントを構成します。 このトピックで説明するタスクを完了すると展開される中央管理ストアが利用できるようになるまで、トポロジ ドキュメントを公開することはできません。 
  

