---
title: 音声ルーティング構成に保留中の変更を公開Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '概要: [コントロール パネル] コントロール パネルを使用して、Skype for Business Serverの音声ルーティング構成の変更を確認、発行、または取り消Skype for Business Server説明します。'
---

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>音声ルーティング構成に保留中の変更を公開Skype for Business
 
**概要:**[コントロール パネル] を使用して、音声ルーティング構成の変更を確認、発行、またはSkype for Business Serverする方法Skype for Business Server説明します。
  
[音声ルーティング] グループのページの構成設定に変更を加えた後、この手順を実行して、保留中の変更を確認、発行、または取り消します。
  
> [!IMPORTANT]
> 一度に 1 人のユーザーだけが音声ルーティング構成設定を変更します。 
  
> [!NOTE]
> すべての保留中の変更は、すべてのコミット コマンドを実行して同時 **に公開する必要** があります。 保留中の変更を選択的に公開することはできません。 保留中の変更を発行する前に、[コミットされていない変更の確認] コマンドを実行し、発行しない構成変更を取り消します。
  
> [!NOTE]
> 保留中の変更をコミットする前に、 **Voice Routing** グループ内のページから移動すると、保留中のすべての変更が失われます。 ただし、現在の構成 (保留中の変更を含む) を音声構成ファイルにエクスポートし、更新された構成をインポートして発行できます。 詳細については、「音声ルート構成[ファイルをエクスポートまたは](voice-route-configuration-import-export.md)インポートする」を参照Skype for Business。 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>音声ルーティング構成の変更を確認、発行、またはキャンセルするには

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator**、**CsServerAdministrator、または CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. 音声ルーティング グループの各ページの設定に必要な構成変更 **を行** います。
    
5. 公開せずに保留中の変更を確認するには、[コミット] メニューから [コミットされていない変更 **を** 確認する] **を選択** します。
    
6. 保留中の変更を取り消す場合は、次のいずれかを実行します。
    
   - [コミット **] メニューの [コミットされていないすべての** 変更を取り消す] **を選択** します。
    
   - キャンセルする保留中の変更がある  [音声ルーティング] ページのタブに移動し、保留中の変更があるアイテムを選択し、[コミット] をクリックし、[選択した変更をキャンセル] をクリック **します。**
    
7. 保留中のすべての変更を確認し、発行しない変更を取り消したら、[コミット] をクリックし、[すべてコミット] **をクリックします**。
    
8. 保留中のすべての **変更の** 一設定表示される [コミットされていない音声構成] ダイアログ ボックスで、[OK] をクリック **します**。 
    
    コントロール Skype for Business Serverが変更をコミットすると、正常に発行された音声ルーティング構成メッセージ **が** 表示されます。
    

