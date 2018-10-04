---
title: SBA のレジストラーの設定の拡張
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 弾力性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: db69f930dfa747e7537e529ede3b90405867ca27
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372707"
---
# <a name="registrar-sba-settings-expander"></a>SBA のレジストラーの設定の拡張

**弾力性**の設定を編集し、次のプロパティを構成します。

- 一覧から**ユーザーの関連付けられているサービスおよびバックアップ レジストラー プール**を選択します。

    必要に応じて、**自動フェイル オーバーおよびフェイル バック音声**のチェック ボックスを選択します。

    **音声障害検出の間隔 (秒)** と**音声のフェイル バックの間隔 (秒)** を構成します。 既定では、間隔は、音声障害を検出するための 120 秒ボイスのフェイル バックの 240 秒です。

    > [!CAUTION]
    > 復元が期待どおりに動作するためには、フェイル オーバーとフェイル バックの間隔を定義する秒数を慎重にテストする必要があります。 間隔を低に設定する (つまりより小さい 120 秒) や、フェイル オーバーとフェイル バックの設定が非常に密接に実際のフェールオーバーおよびフェールバックが期待どおりに動作していません。

  [**OK**]: ダイアログでの変更を受け入れて確定します。

  [**キャンセル**]: 変更を破棄してダイアログを閉じます。

  [**ヘルプ**]: このヘルプ画面を表示します。

## <a name="see-also"></a>関連項目

[エンタープライズ VoIP の復元の計画](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)