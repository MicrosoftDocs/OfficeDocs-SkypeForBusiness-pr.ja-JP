---
title: Skype for Business Server で SIP トランク構成設定をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '概要: Skype for Business Server 管理シェルを使用して、SIP トランク構成設定をテストする方法について説明します。'
ms.openlocfilehash: 1ef034f0b1de187e472fc3049573e9453e5a9505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240109"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="dfb54-103">Skype for Business Server で SIP トランク構成設定をテストする</span><span class="sxs-lookup"><span data-stu-id="dfb54-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="dfb54-104">**概要:** Skype for Business Server 管理シェルを使用して、SIP トランク構成設定をテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfb54-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="dfb54-p101">SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch eXchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係と機能を定義します。たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="dfb54-107">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="dfb54-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="dfb54-108">Realtime Transport Control Protocol (RTCP) パケットが送信される条件。</span><span class="sxs-lookup"><span data-stu-id="dfb54-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="dfb54-109">各トランクで Secure Realtime Transport Protocol (SRTP) 暗号化を要求するか。</span><span class="sxs-lookup"><span data-stu-id="dfb54-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="dfb54-110">Skype for Business Server をインストールすると、SIP トランク構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="dfb54-111">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="dfb54-112">管理者は、Test-CsTrunkConfiguration コマンドレットを使用して、ユーザーがダイヤルした番号をゲートウェイで処理可能な番号にトランクが変換できるかどうかも確認できます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="dfb54-113">トランク構成設定は、Windows PowerShell と [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) コマンドレットを使用する方法でのみテストできます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="dfb54-114">このコマンドレットは、Skype for Business Server 管理シェルから、または Skype for Business Server 管理シェルのリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="dfb54-115">SIP トランク構成設定をテストするには</span><span class="sxs-lookup"><span data-stu-id="dfb54-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="dfb54-116">このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="dfb54-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


