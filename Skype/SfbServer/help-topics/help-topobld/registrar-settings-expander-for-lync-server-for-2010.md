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
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: '[復元] の設定を編集し、以下のプロパティを構成します。'
ms.openlocfilehash: 4271203bf9f737034796cc3b74c95836480df521
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217178"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="691fd-103">Lync Server 2010 用のレジストラー設定の展開</span><span class="sxs-lookup"><span data-stu-id="691fd-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="691fd-104">[**復元**] の設定を編集し、以下のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="691fd-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="691fd-105">リストから [**関連付けられているバックアップ レジストラー プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="691fd-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="691fd-106">必要に応じて、[**音声に対する自動フェールオーバーとフェールバック**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="691fd-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="691fd-p101">[**音声のエラー検出間隔 (秒)**] と [**音声のフェールバック間隔 (秒)**] を構成します。既定では、音声エラー検出の間隔は 120 秒、音声フェールバックの間隔は 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="691fd-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="691fd-p102">復元が意図したとおりに動作するように、フェールオーバーおよびフェールバックの間隔に対して定義する秒数を慎重にテストする必要があります。間隔の設定が短すぎる場合 (120 秒未満) またはフェールオーバーとフェールバックの設定の差が小さすぎる場合は、実際のフェールオーバーおよびフェールバックが意図したとおりに動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="691fd-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="691fd-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="691fd-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="691fd-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="691fd-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="691fd-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="691fd-113">**Help** Displays this help screen.</span></span>
  

