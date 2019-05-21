---
title: Skype for Business のボイスルート構成ファイルをエクスポートまたはインポートする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '概要: skype for business server コントロールパネルを使用して、Skype for Business Server でボイスルーティング構成ファイルをエクスポートまたはインポートする方法について説明します。'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300881"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Skype for Business のボイスルート構成ファイルをエクスポートまたはインポートする
 
**概要:** Skype for business Server コントロールパネルを使用して、Skype for Business Server でボイスルーティング構成ファイルをエクスポートまたはインポートする方法について説明します。
  
音声ルーティング構成を公開せずに保存する場合、この手順を実行して、音声ルーティング構成のスナップショットを保存して取得します。 
  
ボイスルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Skype for Business Server コントロールパネルの [**ボイスルーティング**] グループのページには、は、音声ルーティングのコミットされていない変更です。 こうした未確定の変更は、調整が必要な 2 つの構成間の相違です。
  
グループ内の任意のページの設定にコミットされていない変更を加えた場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。 これにより、変更を公開する前に、複数のセッション中にボイスルーティング構成の変更を行うことができます。 
  
### <a name="to-export-a-voice-routing-configuration"></a>音声ルーティング構成をエクスポートするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**アクション**] メニューの [**構成のエクスポート**] をクリックします。
    
5. 場所とファイル名を指定し、[**保存**] をクリックします。
    
### <a name="to-import-a-voice-routing-configuration"></a>音声ルーティング構成をインポートするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**操作**] メニューの [**構成のインポート**] をクリックします。
    
5. インポートする構成ファイルを検索し、[**開く**] をクリックします。
    
6. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    > [!NOTE]
    > 音声構成ファイルをインポートする場合は、必ず [**すべて確定**] コマンドを実行して構成変更を公開する必要があります。 詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。
  

