---
title: Skype for Business Server での SIP トランク構成設定のテスト
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
ms.openlocfilehash: 1489fe1e45223bac6b62ed23a09212a569ea7838
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826187"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1a698-103">Skype for Business Server での SIP トランク構成設定のテスト</span><span class="sxs-lookup"><span data-stu-id="1a698-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="1a698-p101">SIP トランクの構成では、仲介サーバーと、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) のいずれかとの間の関係および機能を定義します。たとえば、次の設定ができます。</span><span class="sxs-lookup"><span data-stu-id="1a698-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="1a698-106">トランクでメディア バイパスを有効化するか。</span><span class="sxs-lookup"><span data-stu-id="1a698-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="1a698-107">Real-time Transport Control Protocol (RTCP) パケットが送信される条件。</span><span class="sxs-lookup"><span data-stu-id="1a698-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="1a698-108">各トランクでセキュア リアルタイム プロトコル (SRTP) 暗号化を要求するか。</span><span class="sxs-lookup"><span data-stu-id="1a698-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="1a698-109">Skype for Business Server をインストールすると、SIP トランク構成設定のグローバル コレクションが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a698-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="1a698-110">また、管理者はサイト スコープまたはサービス スコープ (PSTN ゲートウェイ サービスの場合のみ) でカスタム設定のコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1a698-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="1a698-111">管理者は [、Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) コマンドレットを使用して、ユーザーがダイヤルした番号をゲートウェイが処理できる番号にトランクが変換できる状態にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a698-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="1a698-112">トランク構成設定は、Windows PowerShell と Test-CsTrunkConfiguration コマンドレットを使用する方法でのみテストできます。</span><span class="sxs-lookup"><span data-stu-id="1a698-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="1a698-113">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a698-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="1a698-114">**SIP トランク構成設定をテストするには**</span><span class="sxs-lookup"><span data-stu-id="1a698-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="1a698-115">このコマンドを実行すると、ダイヤルされた番号 4255551212 がレドモンド サイトのトランク構成設定によって正しく変換できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a698-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
