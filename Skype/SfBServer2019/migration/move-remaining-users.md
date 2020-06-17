---
title: 残りのユーザーを移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、新しい Skype for business Server 2019 の展開にユーザーを移動することができます。 Skype for Business Server 2019 にスムーズに移行できるようにするには、いくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件の詳細については、「Configure clients for migration」を参照してください。 ユーザーの移動の詳細な手順については、「フェーズ 4: テストユーザーをパイロットプールに移動する」を参照してください。'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753715"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>残りのユーザーの Skype for Business Server 2019 への移動

Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使用して、新しい Skype for business Server 2019 の展開にユーザーを移動することができます。 Skype for Business Server 2019 にスムーズに移行できるようにするには、いくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件の詳細については、「 [Configure clients for migration](configure-clients-for-migration.md)」を参照してください。 ユーザーの移動の詳細な手順については、「[フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。
  
> [!IMPORTANT]
> Active Directory ユーザーとコンピュータースナップインまたは従来の管理ツールを使用して、レガシ環境から Skype for Business Server 2019 にユーザーを移動することはできません。 
  
ユーザーを Skype for Business Server 2019 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられたバックエンドデータベースに移動されます。 
  
> [!IMPORTANT]
> これには、レガシ ユーザーによって作成されたアクティブな会議が含まれます。 たとえば、従来のユーザーが**会議**の会議を構成している場合、ユーザーが移動された後も、新しい Skype For business Server 2019 プールでその会議を利用できるようになります。 会議へのアクセスに使用する**会議 URL と電話会議 ID** も同じです。 唯一の違いは、会議が従来のプールではなく、Skype for Business Server 2019 プールでホストされるようになったことです。 
  
> [!NOTE]
> Skype for Business Server 2019 上のホームユーザーは、アップグレードされたクライアントを同時に展開する必要はありません。 クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。 
  
### <a name="post-migration-task"></a>移行後のタスク

1. ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。 
    
2. Skype for Business Server 2019 に所属するユーザーによって開催された会議が、従来のインストールに所属しているフェデレーションユーザーとシームレスに機能するようにするには、移行したユーザーに割り当てられている会議ポリシーで匿名の参加者を許可する必要があります。
    
3. 匿名参加者に許可されている会議ポリシーにより、参加者は、Skype for business Server 2019 コントロールパネルで選択した**匿名ユーザーを招待でき**、Skype For Business Server 管理シェルの**get-csconferencingpolicy**コマンドレットからの出力で**AllowAnonymousParticipantsInMeetings**が**True**に設定されています。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

