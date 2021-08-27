---
title: 音声ルート構成ファイルをエクスポートまたはインポートSkype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '概要: [コントロール パネル] を使用して、音声ルーティング構成ファイルを Skype for Business ServerまたはインポートするSkype for Business Server説明します。'
ms.openlocfilehash: bbad8ca1a9d11074bb99fcd9655b8a8281953344
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626149"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>音声ルート構成ファイルをエクスポートまたはインポートSkype for Business
 
**概要:**[コントロール パネル] を使用して、音声ルーティング構成ファイルを Skype for Business Serverまたはインポートする方法Skype for Business Server説明します。
  
音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、音声ルーティング構成のスナップショットを保存および取得します。 
  
音声ルーティング構成ファイル (.vcfg) をインポートしたが、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Skype for Business Serverコントロール パネルの音声ルーティング グループのページは、音声ルーティングに対してコミットされていない変更が行われたことを示します。 これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。
  
グループ内の任意のページの設定にコミットされていない変更を行った場合、その変更はエクスポートされた音声構成ファイル (.vcfg) に保存されます。 これにより、変更を公開する前に、複数のセッション中に音声ルーティング構成を変更できます。 
  
### <a name="to-export-a-voice-routing-configuration"></a>音声ルーティング構成をエクスポートするには

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator 、CsServerAdministrator、** または **CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**アクション**] メニューの [**構成のエクスポート**] をクリックします。
    
5. 場所とファイル名を指定し、[**保存**] をクリックします。
    
### <a name="to-import-a-voice-routing-configuration"></a>音声ルーティング構成をインポートするには

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator 、CsServerAdministrator、** または **CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**操作**] メニューの [**構成のインポート**] をクリックします。
    
5. インポートする構成ファイルを検索し、[**開く**] をクリックします。
    
6. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    > [!NOTE]
    > 音声構成ファイルをインポートする場合は、必ず [**すべて確定**] コマンドを実行して構成変更を公開する必要があります。 詳細については、「操作」のドキュメントの「音声ルーティング構成[に](voice-route-config-changes.md)保留中の変更Skype for Businessを発行する」を参照してください。
  

