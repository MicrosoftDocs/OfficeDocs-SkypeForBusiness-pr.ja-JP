---
title: Skype for Business での音声ルーティング構成に対する保留中の変更の公開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '概要: Skype for Business Server コントロール パネルを使用して、Skype for Business Server の音声ルーティング構成の変更を確認、公開、または取り消す方法について説明します。'
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830397"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Skype for Business での音声ルーティング構成に対する保留中の変更の公開
 
**概要:** Skype for Business Server コントロール パネルを使用して、Skype for Business Server の音声ルーティング構成の変更を確認、公開、または取り消す方法について説明します。
  
音声ルーティング グループ内のページの構成設定に変更を加えた後、この手順を実行して保留中の変更を確認、公開、または取り消します。
  
> [!IMPORTANT]
> 一度に 1 人のユーザーだけが音声ルーティング構成設定を変更します。 
  
> [!NOTE]
> 保留中のすべての変更は、[すべての確定] コマンドを実行して同時 **に公開する必要** があります。 保留中の変更を選択的に公開することはできません。 保留中の変更を公開する前に、[コミットされていない変更の確認] コマンドを実行し、公開しない構成の変更を取り消します。
  
> [!NOTE]
> 保留中の変更をコミットする前に音声ルーティング グループ内のページから移動すると、保留中のすべての変更が失われます。 ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートし、更新された構成をインポートして発行できます。 詳細については [、「Skype for Business でのボイス ルート構成ファイルのエクスポートまたはインポート」を参照してください](voice-route-configuration-import-export.md)。 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>音声ルーティング構成の変更を確認、公開、または取り消す方法

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、****または****CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. 音声ルーティング グループの各ページの設定に必要な構成変更 **を行** います。
    
5. 保留中の変更を公開せずに確認するには、[コミット] メニューの [ **コミット** されていない変更の確認] **を選択** します。
    
6. 保留中の変更を取り消す場合は、次のいずれかを実行します。
    
   - [ **コミット] メニューから [コミットされていないすべての変更** を取り消す] **を選択** します。
    
   - 取り消す保留中の変更がある [音声ルーティング] ページのタブに移動し、保留中の変更があるアイテムを選択し、[確定] をクリックして、[選択した変更の取り消し] をクリック **します。**
    
7. 保留中のすべての変更を確認し、公開しない変更を取り消したら、[確定] をクリックし、[すべて確定] を **クリックします**。
    
8. 保留中のすべての **変更の一覧を** 表示する [コミットされていない音声構成設定] ダイアログ ボックスで **、[OK]** をクリックします。 
    
    Skype for Business Server コントロール パネルが変更をコミットすると、正常に公開された音声ルーティング **構成メッセージが** 表示されます。
    

