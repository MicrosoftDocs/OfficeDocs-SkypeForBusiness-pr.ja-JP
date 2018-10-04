---
title: 2010 Lync Server のレジストラーの設定の拡張
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 弾力性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: 5d6fffdadeb96ed72caf9478cbcaefe754d8e24c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374056"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="72474-103">2010 Lync Server のレジストラーの設定の拡張</span><span class="sxs-lookup"><span data-stu-id="72474-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="72474-104">**弾力性**の設定を編集し、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="72474-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="72474-105">**関連バックアップ レジストラー プール**をリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="72474-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="72474-106">必要に応じて、**自動フェイル オーバーおよびフェイル バック音声**のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="72474-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="72474-107">**音声障害検出の間隔 (秒)** と**音声のフェイル バックの間隔 (秒)** を構成します。</span><span class="sxs-lookup"><span data-stu-id="72474-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="72474-108">既定では、間隔は、音声障害を検出するための 120 秒ボイスのフェイル バックの 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="72474-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="72474-109">復元が期待どおりに動作するためには、フェイル オーバーとフェイル バックの間隔を定義する秒数を慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72474-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="72474-110">間隔を低に設定する (つまりより小さい 120 秒) や、フェイル オーバーとフェイル バックの設定が非常に密接に実際のフェールオーバーおよびフェールバックが期待どおりに動作していません。</span><span class="sxs-lookup"><span data-stu-id="72474-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="72474-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="72474-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="72474-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="72474-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="72474-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="72474-113">**Help** Displays this help screen.</span></span>
  

