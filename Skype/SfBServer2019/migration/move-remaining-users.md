---
title: 残りのユーザーの移動
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for business server コントロールパネルまたは Skype for Business Server Management Shell を使用して、ユーザーを新しい Skype for Business Server 2019 の展開に移動することができます。 Skype for Business Server 2019 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。 このトピックの手順を完了するための前提条件の詳細については、「移行のためにクライアントを構成する」を参照してください。 ユーザーの移動の詳細な手順については、「フェーズ 4: テストユーザーをパイロットプールに移動する」を参照してください。'
ms.openlocfilehash: ac384e9f9e4aaaa534f5b646f1d847485dbb4c23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813265"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>残りのユーザーを Skype for Business Server 2019 に移動する

Skype for business server コントロールパネルまたは Skype for Business Server Management Shell を使用して、ユーザーを新しい Skype for Business Server 2019 の展開に移動することができます。 Skype for Business Server 2019 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。 このトピックの手順を完了するための前提条件の詳細については、「[移行のためにクライアントを構成](configure-clients-for-migration.md)する」を参照してください。 ユーザーの移動の詳細な手順については、「[フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。
  
> [!IMPORTANT]
> Active Directory ユーザーとコンピューターのスナップインまたは従来の管理ツールを使用して、従来の環境から Skype for Business Server 2019 にユーザーを移動することはできません。 
  
ユーザーを Skype for Business Server 2019 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられているバックエンドデータベースに移動されます。 
  
> [!IMPORTANT]
> これには、従来のユーザーによって作成されたアクティブな会議も含まれます。 たとえば、従来のユーザーが**会議**用の会議を構成している場合は、ユーザーが移動された後も、新しい Skype For business Server 2019 プールでその会議を利用できます。 会議にアクセスするための詳細は、会議の**URL と会議 ID と**同じである必要があります。 唯一の違いは、会議が Skype for Business Server 2019 プールでホストされ、従来のプールではホストされていないことです。 
  
> [!NOTE]
> Skype for Business Server 2019 のホームユーザーは、アップグレードされたクライアントを展開する必要はありません。 新しい機能は、ユーザーが新しいクライアントソフトウェアにアップグレードした場合にのみ利用可能になります。 
  
### <a name="post-migration-task"></a>移行後の作業

1. ユーザーを移動した後、それらに割り当てられている会議ポリシーを確認します。 
    
2. Skype for Business Server 2019 を使っているユーザーによって開催された会議が、レガシインストールのあるフェデレーションユーザーとシームレスに動作するようにするには、移行したユーザーに割り当てられている会議ポリシーを使用して、匿名の参加者を許可する必要があります。
    
3. 匿名の参加者が Skype for business Server 2019 コントロールパネルで選択された**匿名ユーザーを招待する**ことを許可する会議ポリシーで、Skype For Business Server 管理シェルの**set-csconferencingpolicy**コマンドレットの出力で**AllowAnonymousParticipantsInMeetings**を**True**に設定している。 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

