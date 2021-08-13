---
title: 残りのユーザーの移動
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
description: 'コントロール パネルまたは管理シェルを使用して、Skype for Business Server 2019 Skype for Business Server 2019 Skype for Business Serverにユーザーを移動できます。 2019 年から 2019 年までスムーズに移行するには、いくつかの要件Skype for Business Serverがあります。 このトピックの手順を完了するための前提条件の詳細については、「移行用にクライアントを構成する」を参照してください。 ユーザーの移動の詳細な手順については、「フェーズ 4: テスト ユーザーをパイロット プールに移動する」を参照してください。'
ms.openlocfilehash: a2742acf32899aca71c28da733c723640a8c1e9200f26f793a918eac04714f15
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300633"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>残りのユーザーを 2019 Skype for Business Serverに移動する

コントロール パネルまたは管理シェルを使用して、Skype for Business Server 2019 Skype for Business Server 2019 Skype for Business Serverにユーザーを移動できます。 2019 年から 2019 年までスムーズに移行するには、いくつかの要件Skype for Business Serverがあります。 このトピックの手順を完了するための前提条件の詳細については、「移行用にクライアントを構成 [する」を参照してください](configure-clients-for-migration.md)。 ユーザーの移動の詳細な手順については、「フェーズ 4: テスト ユーザーをパイロット プールに [移動する」を参照してください](phase-4-move-test-users-to-the-pilot-pool.md)。
  
> [!IMPORTANT]
> Active Directory Users and Computers スナップインまたは従来の管理ツールを使用して、ユーザーを従来の環境から 2019 年Skype for Business Serverすることはできません。 
  
ユーザーを Skype for Business Server 2019 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられたバック エンド データベースに移動されます。 
  
> [!IMPORTANT]
> これには、レガシ ユーザーによって作成されたアクティブな会議が含まれます。 たとえば、従来のユーザーが自分の会議会議を構成している場合、その会議は、ユーザーの移動後も新しい Skype for Business Server Skype for Business Server 2019 プールで使用できます。 会議へのアクセスに使用する **会議 URL と電話会議 ID** も同じです。 唯一の違いは、会議が従来のプールではなく、Skype for Business Server 2019 プールでホストされている点です。 
  
> [!NOTE]
> 2019 年 2019 Skype for Business Serverユーザーをホーミングしても、アップグレードされたクライアントを同時に展開する必要はない。 クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。 
  
### <a name="post-migration-task"></a>移行後のタスク

1. ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。 
    
2. Skype for Business Server 2019 に参加しているユーザーが組織した会議が、従来のインストールに参加しているフェデレーション ユーザーとシームレスに連携するために、移行されたユーザーに割り当てられた会議ポリシーで匿名参加者を許可する必要があります。
    
3. 匿名参加者を許可する会議ポリシーでは、Skype for Business Server 2019 コントロール パネルで選択した匿名ユーザーを参加者に招待し、Skype for Business Server 管理シェルの **Get-CsConferencingPolicy** コマンドレットからの出力で **AllowAnonymousParticipantsInMeetings** を True に設定します。   
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

