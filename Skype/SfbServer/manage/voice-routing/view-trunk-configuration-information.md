---
title: Skype for Business Server でトランク構成情報を表示する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102993"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="4aa6b-103">Skype for Business Server でトランク構成情報を表示する</span><span class="sxs-lookup"><span data-stu-id="4aa6b-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="4aa6b-104">SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="4aa6b-105">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="4aa6b-106">Real-time Transport Control Protocol (RTCP) パケットが送信される条件。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="4aa6b-107">各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="4aa6b-108">Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="4aa6b-109">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="4aa6b-110">**Skype for Business Server コントロール パネルを使用して SIP トランク構成情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="4aa6b-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="4aa6b-111">Skype for Business Server コントロールパネルで、[音声ルーティング] をクリックし、[トランク構成]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="4aa6b-112">[トランク **構成] タブ** に、すべてのトランク構成設定コレクションの一覧が表示されます。各コレクションには、**名前**、**スコープ**、状態、およびメディアバイパス プロパティの値と **、PSTN** 使用法の数、電話番号ルール、およびコレクションに関連付けられた呼び出し番号ルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="4aa6b-113">トランク構成設定のコレクションの詳細を表示するには、関心のあるコレクションをクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="4aa6b-114">一度に 1 つのトランク構成設定のコレクションについてのみ詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4aa6b-115">SIP トランク構成情報を表示する場合は、Windows PowerShellコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4aa6b-116">SIP トランク構成の設定は、Skype for Business Server PowerShell および Get-CsTrunkConfigurationコマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="4aa6b-117">このコマンドレットは、Skype for Business Server 管理シェルから、またはリモート セッション から実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="4aa6b-118">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、Lync Server Windows PowerShell ブログ記事「クイック スタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理」を https://go.microsoft.com/fwlink/p/?linkId=255876 参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="4aa6b-119">このリンクを置換または削除します。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="4aa6b-120">**SIP トランク構成情報を表示するには**</span><span class="sxs-lookup"><span data-stu-id="4aa6b-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="4aa6b-121">すべての SIP トランク構成設定に関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="4aa6b-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="4aa6b-123">詳細については [、Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa6b-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>