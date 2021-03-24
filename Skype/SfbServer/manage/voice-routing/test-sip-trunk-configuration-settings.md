---
title: Skype for Business Server で SIP トランク構成設定をテストする
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
description: 'SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。 '
ms.openlocfilehash: 87f5b8aa07a7545f30f1d0e8b81b33197ea704c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103023"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="21173-103">Skype for Business Server で SIP トランク構成設定をテストする</span><span class="sxs-lookup"><span data-stu-id="21173-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="21173-p101">SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="21173-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="21173-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="21173-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="21173-107">Real-time Transport Control Protocol (RTCP) パケットが送信される条件。</span><span class="sxs-lookup"><span data-stu-id="21173-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="21173-108">各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。</span><span class="sxs-lookup"><span data-stu-id="21173-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="21173-109">Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="21173-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="21173-110">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="21173-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="21173-111">管理者は [、Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) コマンドレットを使用して、トランクがユーザーがダイヤルした番号をゲートウェイで処理できる番号に変換できる可能性を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="21173-111">Administrators can also use the [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="21173-112">トランク構成設定は、Windows PowerShell と Test-CsTrunkConfiguration コマンドレットを使用する方法でのみテストできます。</span><span class="sxs-lookup"><span data-stu-id="21173-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="21173-113">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="21173-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="21173-114">**SIP トランク構成設定をテストするには**</span><span class="sxs-lookup"><span data-stu-id="21173-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="21173-115">このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="21173-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```