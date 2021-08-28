---
title: Lync Server 2010 用のレジストラー設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: '[復元] の設定を編集し、以下のプロパティを構成します。'
ms.openlocfilehash: ee7013e71c687ca3645a9f4d708703f335f256b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629729"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Lync Server 2010 用のレジストラー設定エキスパンダー
 
[**復元**] の設定を編集し、以下のプロパティを構成します。
  
- リストから [**関連付けられているバックアップ レジストラー プール**] を選択します。
    
    必要に応じて、[**音声に対する自動フェールオーバーとフェールバック**] チェック ボックスをオンにします。
    
    [**音声のエラー検出間隔 (秒)**] と [**音声のフェールバック間隔 (秒)**] を構成します。既定では、音声エラー検出の間隔は 120 秒、音声フェールバックの間隔は 240 秒です。
    
    > [!CAUTION]
    > 復元が意図したとおりに動作するように、フェールオーバーおよびフェールバックの間隔に対して定義する秒数を慎重にテストする必要があります。間隔の設定が短すぎる場合 (120 秒未満) またはフェールオーバーとフェールバックの設定の差が小さすぎる場合は、実際のフェールオーバーおよびフェールバックが意図したとおりに動作しない可能性があります。 
  
  [**OK**]: ダイアログでの変更を受け入れて確定します。
  
  [**キャンセル**]: 変更を破棄してダイアログを閉じます。
  
  [**ヘルプ**]: このヘルプ画面を表示します。
  

