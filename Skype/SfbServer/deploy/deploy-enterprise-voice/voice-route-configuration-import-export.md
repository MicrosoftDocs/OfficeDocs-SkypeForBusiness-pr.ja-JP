---
title: ビジネス用 Skype でのボイス ルート構成ファイルをインポートまたはエクスポート
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '概要: ビジネス サーバーのビジネス サーバーのコントロール パネルの Skype を使用して、Skype で音声ルーティング構成ファイルをインポートまたはエクスポートする方法を説明します。'
ms.openlocfilehash: 8f0d8f4e221cbe23ac37c4126a9d26aac46e6d53
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222473"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>ビジネス用 Skype でのボイス ルート構成ファイルをインポートまたはエクスポート
 
**の概要:** Business Server のビジネス サーバーのコントロール パネルの Skype を使用して、Skype で音声ルーティング構成ファイルをインポートまたはエクスポートする方法について説明します。
  
音声ルーティング構成を公開せずに保存する場合、この手順を実行して、音声ルーティング構成のスナップショットを保存して取得します。 
  
音声ルーティング構成ファイル (.vcfg) をインポートしても、音声ルーティングの構成、サーバーの間に変更が加えられて、Skype ビジネス サーバーのコントロール パネルの [**音声のルーティング**グループ内のページが表示されますがあります。ルーティングを音声にコミットされていない変更は。 こうした未確定の変更は、調整が必要な 2 つの構成間の相違です。
  
グループ内の任意のページの設定をコミットされていない変更を加えた場合、変更は、エクスポートされた音声構成ファイル (.vcfg) に保存されます。 これにより、音声の変更を発行する前に複数のセッション中に構成の変更をルーティングすることができます。 
  
### <a name="to-export-a-voice-routing-configuration"></a>音声ルーティング構成をエクスポートするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**アクション**] メニューの [**構成のエクスポート**] をクリックします。
    
5. 場所とファイル名を指定し、[**保存**] をクリックします。
    
### <a name="to-import-a-voice-routing-configuration"></a>音声ルーティング構成をインポートするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**操作**] メニューの [**構成のインポート**] をクリックします。
    
5. インポートする構成ファイルを検索し、[**開く**] をクリックします。
    
6. [**確定**] をクリックし、[**すべて確定**] をクリックします。
    
    > [!NOTE]
    > 音声構成ファイルをインポートする場合は、必ず [**すべて確定**] コマンドを実行して構成変更を公開する必要があります。 詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。
  

