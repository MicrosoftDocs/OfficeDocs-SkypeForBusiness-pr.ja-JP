---
title: Skype for Business でボイス ルート構成ファイルをエクスポートまたはインポートする
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '概要: Skype for Business Server コントロール パネルを使用して、Skype for Business Server で音声ルーティング構成ファイルをエクスポートまたはインポートする方法について説明します。'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830357"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Skype for Business でボイス ルート構成ファイルをエクスポートまたはインポートする
 
**概要:** Skype for Business Server コントロール パネルを使用して、Skype for Business Server で音声ルーティング構成ファイルをエクスポートまたはインポートする方法について説明します。
  
音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、音声ルーティング構成のスナップショットを保存して取得します。 
  
音声ルーティング構成ファイル (.vcfg) をインポートし、その間にサーバー上の音声ルーティング構成が変更された場合、Skype for Business  Server コントロール パネルの音声ルーティング グループのページには、音声ルーティングにコミットされていない変更が含まれています。 これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。
  
グループ内の任意のページの設定にコミットされていない変更を行った場合、その変更はエクスポートされた音声構成ファイル (.vcfg) に保存されます。 これにより、変更を公開する前に、複数のセッションで音声ルーティング構成を変更できます。 
  
### <a name="to-export-a-voice-routing-configuration"></a>音声ルーティング構成をエクスポートするには

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、****または****CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**アクション**] メニューの [**構成のエクスポート**] をクリックします。
    
5. 場所とファイル名を指定し、[**保存**] をクリックします。
    
### <a name="to-import-a-voice-routing-configuration"></a>音声ルーティング構成をインポートするには

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、****または****CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**操作**] メニューの [**構成のインポート**] をクリックします。
    
5. インポートする構成ファイルを検索し、[**開く**] をクリックします。
    
6. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    > [!NOTE]
    > 音声構成ファイルをインポートする場合は、必ず [**すべて確定**] コマンドを実行して構成変更を公開する必要があります。 詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。
  

