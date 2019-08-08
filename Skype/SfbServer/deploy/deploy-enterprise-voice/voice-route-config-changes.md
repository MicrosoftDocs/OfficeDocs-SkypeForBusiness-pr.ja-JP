---
title: Skype for Business の音声ルーティング構成に保留中の変更を公開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '概要: skype for business Server コントロールパネルを使用して、Skype for Business Server のボイスルーティング構成の変更を確認、発行、またはキャンセルする方法について説明します。'
ms.openlocfilehash: 6a13c2a2b2b1221203fbed84948b803a6c2ea1db
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239923"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Skype for Business の音声ルーティング構成に保留中の変更を公開する
 
**概要:** Skype for business Server コントロールパネルを使用して、Skype for Business Server の音声ルーティング構成の変更を確認、発行、またはキャンセルする方法について説明します。
  
[**音声ルーティング**] グループの各ページで会議設定のいずれかを変更した後は、ここでの手順を実行して、保留中の変更を確認、公開、またはキャンセルします。
  
> [!IMPORTANT]
> 必ず、一度に 1 人のユーザーだけが音声ルーティング構成の設定を変更するようにしてください。 
  
> [!NOTE]
> 保留中の変更すべては、[**すべて確定**] コマンドを実行することによって同時に公開する必要があります。保留中の変更のどれかを選択して公開することはできません。保留中の変更を公開する前に、[**未確定の変更の確認**] コマンドを実行し、公開しない保留中の変更をすべてキャンセルしてください。
  
> [!NOTE]
> 保留中の変更を確定する前に [**音声ルーティング**] グループのページから移動して離れると、すべての保留中の変更が失われます。 ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートしておき、後でインポートして更新された構成を公開することができます。 詳細については、「 [Skype For business のボイスルート構成ファイルをエクスポートまたはインポートする](voice-route-configuration-import-export.md)」を参照してください。 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>音声ルーティング構成の変更を確認、公開、または取り消すには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**音声ルーティング**] グループの各ページの設定について、必要な構成の変更を加えます。
    
5. 公開せずに保留中の変更を確認するには、[**確定**] メニューで [**未確定の変更の確認**] を選択します。
    
6. 保留中の変更のいずれかを取り消す場合は、次のいずれかの操作を行います。
    
   - [**確定**] メニューで [**すべての未確定の変更のキャンセル**] を選択します。
    
   - 取り消す保留中の変更が含まれる [**音声ルーティング**] ページのタブに移動し、保留中の変更を含む項目を選択し、[**確定**] をクリックして、[**選択した変更のキャンセル**] をクリックします。
    
7. 保留中の変更をすべて確認し、公開しない変更をすべてキャンセルしたら、[**確定**] をクリックして、[**すべて確定**] をクリックします。
    
8. 保留中の変更すべての一覧が表示された [**未確定の音声構成設定**] ダイアログ ボックスで、[**OK**] をクリックします。 
    
    Skype for Business Server コントロールパネルが変更をコミットすると、**正常に公開された音声ルーティング構成**のメッセージが表示されます。
    

