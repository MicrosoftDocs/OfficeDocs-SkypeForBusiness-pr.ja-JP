---
title: レジストラー SBA 設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 回復性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: 7eb90efde862b6326ea6f43f27937751ebff0ce9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797248"
---
# <a name="registrar-sba-settings-expander"></a>レジストラー SBA 設定エキスパンダー

**回復性**の設定を編集し、次のプロパティを構成します。

- リストから**関連付けられているユーザーサービスとバックアップレジストラープール**を選択します。

    必要に応じて、[**自動フェールオーバーと音声のフェールバック**] チェックボックスをオンにします。

    **ボイスエラー検出間隔 (sec)** と**ボイスバックの間隔 (秒)** を構成します。 既定では、音声の障害検出と240秒のボイスバックの間隔は120秒です。

    > [!CAUTION]
    > フェールオーバーとフェールバックの間隔に対して定義した秒数は、回復性が期待どおりに動作することを確認するために慎重にテストする必要があります。 間隔を低 (つまり、120秒未満) に設定した場合、またはフェールオーバーとフェールバックがあまりにも設定されていない場合は、実際のフェールオーバーが予期したとおりに機能しないことがあります。

  [**OK**]: ダイアログでの変更を受け入れて確定します。

  [**キャンセル**]: 変更を破棄してダイアログを閉じます。

  [**ヘルプ**]: このヘルプ画面を表示します。

## <a name="see-also"></a>関連項目

[エンタープライズボイスの回復性の計画](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
