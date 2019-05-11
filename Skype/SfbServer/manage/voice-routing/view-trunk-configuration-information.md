---
title: Skype のビジネス サーバーのトランクの構成情報を表示します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。
ms.openlocfilehash: dab6a53d76bdc33ddd39117afd7f8b32a1c9c170
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926087"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="fb615-103">Skype のビジネス サーバーのトランクの構成情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="fb615-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="fb615-104">SIP トランクの構成設定は、仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイ、IP 公開ブランチ交換機 (PBX)、またはサービス プロバイダーのセッション ボーダー コント ローラー (SBC) の間での機能との関係を定義します。</span><span class="sxs-lookup"><span data-stu-id="fb615-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="fb615-105">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="fb615-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="fb615-106">リアルタイム転送制御プロトコル (RTCP) パケットを送信する条件です。</span><span class="sxs-lookup"><span data-stu-id="fb615-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="fb615-107">かどうか各トランクには、セキュリティで保護されたリアルタイム プロトコル (SRTP) 暗号化が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb615-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="fb615-108">ビジネス サーバーの Skype をインストールすると SIP トランク構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb615-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="fb615-109">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fb615-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="fb615-110">**ビジネス サーバーのコントロール パネルの Skype を使用して、SIP トランクの構成情報を表示するのには**</span><span class="sxs-lookup"><span data-stu-id="fb615-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="fb615-111">[ビジネス サーバーのコントロール パネルの Skype、**音声ルーティング**を**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb615-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="fb615-112">[**トランク構成**] タブですべてのトランク構成設定コレクションの一覧が表示されます。コレクションごとに、**名前**、**範囲**、**状態**、および**メディアをバイパス**プロパティの値と、 **PSTN の使用法\*\*\*\*規則の番号を呼び出し**、および**番号の規則と呼ばれる**関連付けられている数が表示されます。コレクションです。</span><span class="sxs-lookup"><span data-stu-id="fb615-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="fb615-113">トランク構成設定のコレクションの詳細情報を表示するには、目的のコレクションをクリックして**編集**を**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb615-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="fb615-114">一度にトランク構成設定の 1 つのコレクションに対してのみ詳細情報を表示できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb615-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb615-115">Windows PowerShell コマンドレットを使用して SIP トランクの構成情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="fb615-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fb615-116">SIP トランクの構成設定は、Skype をビジネス サーバー PowerShell および Get CsTrunkConfiguration コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="fb615-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="fb615-117">ビジネス サーバー管理シェルの Skype から、または Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb615-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="fb615-118">ビジネス サーバーでは、Skype に接続するリモートの Windows PowerShell を使用して詳細に Lync Server の Windows PowerShell のブログ記事「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」を参照してくださいhttp://go.microsoft.com/fwlink/p/?linkId=255876。</span><span class="sxs-lookup"><span data-stu-id="fb615-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="fb615-119">置き換えるか、このリンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb615-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="fb615-120">**SIP トランクの構成情報を表示するのには**</span><span class="sxs-lookup"><span data-stu-id="fb615-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="fb615-121">すべての SIP トランク構成設定に関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fb615-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="fb615-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb615-122">That will return information similar to this:</span></span>

```
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
<span data-ttu-id="fb615-123">詳細については、 [Get CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb615-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



