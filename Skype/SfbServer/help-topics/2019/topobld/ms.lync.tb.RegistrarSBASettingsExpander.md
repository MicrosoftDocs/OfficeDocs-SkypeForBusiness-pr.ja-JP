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
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="4bf51-103">レジストラー SBA 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="4bf51-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="4bf51-104">**回復性**の設定を編集し、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="4bf51-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="4bf51-105">リストから**関連付けられているユーザーサービスとバックアップレジストラープール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bf51-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="4bf51-106">必要に応じて、[**自動フェールオーバーと音声のフェールバック**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4bf51-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="4bf51-107">**ボイスエラー検出間隔 (sec)** と**ボイスバックの間隔 (秒)** を構成します。</span><span class="sxs-lookup"><span data-stu-id="4bf51-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="4bf51-108">既定では、音声の障害検出と240秒のボイスバックの間隔は120秒です。</span><span class="sxs-lookup"><span data-stu-id="4bf51-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="4bf51-109">フェールオーバーとフェールバックの間隔に対して定義した秒数は、回復性が期待どおりに動作することを確認するために慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bf51-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="4bf51-110">間隔を低 (つまり、120秒未満) に設定した場合、またはフェールオーバーとフェールバックがあまりにも設定されていない場合は、実際のフェールオーバーが予期したとおりに機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="4bf51-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="4bf51-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="4bf51-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="4bf51-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4bf51-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="4bf51-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="4bf51-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bf51-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bf51-114">See also</span></span>

[<span data-ttu-id="4bf51-115">エンタープライズボイスの回復性の計画</span><span class="sxs-lookup"><span data-stu-id="4bf51-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
