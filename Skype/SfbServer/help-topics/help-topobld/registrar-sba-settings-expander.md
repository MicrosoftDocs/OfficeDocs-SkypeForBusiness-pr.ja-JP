---
title: レジストラー SBA 設定エキスパンダー
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 弾力性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: 118c7e3eda7fc8422483989880f7ae0b31b9842f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896705"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="510c1-103">レジストラー SBA 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="510c1-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="510c1-104">**弾力性**の設定を編集し、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="510c1-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="510c1-105">一覧から**ユーザーの関連付けられているサービスおよびバックアップ レジストラー プール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="510c1-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="510c1-106">必要に応じて、**自動フェイル オーバーおよびフェイル バック音声**のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="510c1-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="510c1-107">**音声障害検出の間隔 (秒)** と**音声のフェイル バックの間隔 (秒)** を構成します。</span><span class="sxs-lookup"><span data-stu-id="510c1-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="510c1-108">既定では、間隔は、音声障害を検出するための 120 秒ボイスのフェイル バックの 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="510c1-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="510c1-109">復元が期待どおりに動作するためには、フェイル オーバーとフェイル バックの間隔を定義する秒数を慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="510c1-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="510c1-110">間隔を低に設定する (つまりより小さい 120 秒) や、フェイル オーバーとフェイル バックの設定が非常に密接に実際のフェールオーバーおよびフェールバックが期待どおりに動作していません。</span><span class="sxs-lookup"><span data-stu-id="510c1-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="510c1-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="510c1-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="510c1-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="510c1-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="510c1-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="510c1-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="510c1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="510c1-114">See also</span></span>

[<span data-ttu-id="510c1-115">エンタープライズ VoIP の復元の計画</span><span class="sxs-lookup"><span data-stu-id="510c1-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
