---
title: レジストラー SBA 設定エキスパンダー
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
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: '[復元] の設定を編集し、以下のプロパティを構成します。'
ms.openlocfilehash: 33c8ddd4c97a160a574287ccaca0d9d9675bda600e6857b6e5122cf6c22e755f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321709"
---
# <a name="registrar-sba-settings-expander"></a>レジストラー SBA 設定エキスパンダー

[**復元**] の設定を編集し、以下のプロパティを構成します。

- 一覧から [**関連付けられているユーザー サービスとバックアップ レジストラー プール**] を選択します。

    必要に応じて、[**音声に対する自動フェールオーバーとフェールバック**] チェック ボックスをオンにします。

    [**音声のエラー検出間隔 (秒)**] と [**音声のフェールバック間隔 (秒)**] を構成します。既定では、音声エラー検出の間隔は 120 秒、音声フェールバックの間隔は 240 秒です。

    > [!CAUTION]
    > 復元が意図したとおりに動作するように、フェールオーバーおよびフェールバックの間隔に対して定義する秒数を慎重にテストする必要があります。間隔の設定が短すぎる場合 (120 秒未満) またはフェールオーバーとフェールバックの設定の差が小さすぎる場合は、実際のフェールオーバーおよびフェールバックが意図したとおりに動作しない可能性があります。

  [**OK**]: ダイアログでの変更を受け入れて確定します。

  [**キャンセル**]: 変更を破棄してダイアログを閉じます。

  [**ヘルプ**]: このヘルプ画面を表示します。

## <a name="see-also"></a>関連項目

[エンタープライズ VoIP の復旧の計画](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)