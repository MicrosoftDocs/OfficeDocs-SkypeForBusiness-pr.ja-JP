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
ms.openlocfilehash: 48ba2f95cc5cae31d71727d5707120c608ffda6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104413"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="7b670-103">レジストラー SBA 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="7b670-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="7b670-104">[**復元**] の設定を編集し、以下のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b670-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="7b670-105">一覧から [**関連付けられているユーザー サービスとバックアップ レジストラー プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b670-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="7b670-106">必要に応じて、[**音声に対する自動フェールオーバーとフェールバック**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7b670-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="7b670-p101">[**音声のエラー検出間隔 (秒)**] と [**音声のフェールバック間隔 (秒)**] を構成します。既定では、音声エラー検出の間隔は 120 秒、音声フェールバックの間隔は 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="7b670-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="7b670-p102">復元が意図したとおりに動作するように、フェールオーバーおよびフェールバックの間隔に対して定義する秒数を慎重にテストする必要があります。間隔の設定が短すぎる場合 (120 秒未満) またはフェールオーバーとフェールバックの設定の差が小さすぎる場合は、実際のフェールオーバーおよびフェールバックが意図したとおりに動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b670-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="7b670-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="7b670-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="7b670-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7b670-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="7b670-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="7b670-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b670-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b670-114">See also</span></span>

[<span data-ttu-id="7b670-115">エンタープライズ VoIP の復旧の計画</span><span class="sxs-lookup"><span data-stu-id="7b670-115">Planning for Enterprise Voice Resiliency</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)