---
title: Skype for Business Server 2015 の回線共有機能の計画
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: ビジネス サーバー 2015 年 2015年 11 月の共有行の外観 (SLA) で Skype を計画する方法については、このトピックを参照して累積的な更新です。
ms.openlocfilehash: ae19afbffce6f51abd811a0062c611ee130c4e4d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206467"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="c184e-103">Skype for Business Server 2015 の回線共有機能の計画</span><span class="sxs-lookup"><span data-stu-id="c184e-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c184e-104">ビジネス サーバー 2015 年 2015年 11 月の共有行の外観 (SLA) で Skype を計画する方法については、このトピックを参照して累積的な更新です。</span><span class="sxs-lookup"><span data-stu-id="c184e-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="c184e-105">線の外観を共有は、共有の数と呼ばれる特定の番号に複数の呼び出しを処理するためのビジネス用の Skype の機能です。</span><span class="sxs-lookup"><span data-stu-id="c184e-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="c184e-106">SLA は企業を構成することができます音声が有効になって Skype ビジネス ユーザーの共有を付けて複数行に複数の呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="c184e-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="c184e-107">実際には共有番号で通話を受信するのではなく、共有番号の代理人として機能するユーザーに通話が転送されます。</span><span class="sxs-lookup"><span data-stu-id="c184e-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="c184e-108">いずれかの代理人が通話に応答すると、残りの代理人は誰が通話に応答したか、またその結果としてどの回線が通話中になったかを示す通知を自分の電話で受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c184e-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="c184e-109">SLA では、回線の番号と代理人の両方を共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="c184e-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="c184e-110">さらに、BusyOption (すべての回線が通話中のときに実行する処理) と MissedCallOption (通話に応答できる代理人がいない場合の処理) などの高度なオプションも共有番号に対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="c184e-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="c184e-111">SLA は、次の電話デバイス (サポートされていない Skype のビジネス上のクライアント コンピューター、携帯電話、またはその他のデバイス) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c184e-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="c184e-112">Polycom VVX300 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="c184e-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="c184e-113">Polycom VVX400 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="c184e-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="c184e-114">Polycom VVX500 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="c184e-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="c184e-115">Polycom VVX600 (ファームウェア更新プログラム 5.4.1 インストール済み)</span><span class="sxs-lookup"><span data-stu-id="c184e-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="c184e-116">SLA 2015年 11 月ビジネス サーバーでは、Skype の新機能は、累積的な更新です。</span><span class="sxs-lookup"><span data-stu-id="c184e-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="c184e-117">SLA の展開の詳細については、「[Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c184e-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="c184e-118">機能リスト</span><span class="sxs-lookup"><span data-stu-id="c184e-118">Feature List</span></span>

<span data-ttu-id="c184e-119">SLA グループをセットアップすると次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c184e-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="c184e-p102">グループ内のすべての代理人が同じ共有番号への着信通話に応答できます。PSTN ベースまたは SIP ベースの通話を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c184e-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="c184e-122">代理人は、通話に応答することも保留にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c184e-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="c184e-123">代理人は、SLA グループの外部の番号に通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="c184e-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="c184e-124">代理人は、現在の共有番号上の通話数と、それらの各通話のステータスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c184e-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="c184e-p103">共有番号で受信する通話の最大数を構成できます。この最大数に達した後にかかってきた通話の処理方法も設定できます。その後の通話に対しては、話中音を流すか、代替番号に転送するか、ボイス メールに転送できます。</span><span class="sxs-lookup"><span data-stu-id="c184e-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="c184e-p104">不在着信 (一定の時間が経過しても応答されなかった通話) の処理方法を構成できます。グループ ID のボイス メールを有効にした場合、不在着信は自動的にボイス メールに転送されます。グループ ID (共有番号) のボイス メールを有効にしない場合、不在着信に対して話中音を流すか、代替番号に転送するか、切断するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c184e-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

