---
title: Lync Server 2010 用のレジストラー設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 回復性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: 31a8504aecbc14ae2c81ad27a3aaeedbe9e40b66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684420"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Lync Server 2010 用のレジストラー設定の展開
 
**回復性**の設定を編集し、次のプロパティを構成します。
  
- 一覧から [**関連付けられているバックアップレジストラープール**] を選びます。
    
    必要に応じて、[**自動フェールオーバーと音声のフェールバック**] チェックボックスをオンにします。
    
    **ボイスエラー検出間隔 (sec)** と**ボイスバックの間隔 (秒)** を構成します。 既定では、音声の障害検出と240秒のボイスバックの間隔は120秒です。
    
    > [!CAUTION]
    > フェールオーバーとフェールバックの間隔に対して定義した秒数は、回復性が期待どおりに動作することを確認するために慎重にテストする必要があります。 間隔を低 (つまり、120秒未満) に設定した場合、またはフェールオーバーとフェールバックがあまりにも設定されていない場合は、実際のフェールオーバーが予期したとおりに機能しないことがあります。 
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

