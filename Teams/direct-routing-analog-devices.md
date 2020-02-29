---
title: 直接ルーティング-アナログデバイスの接続
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: この記事では、Microsoft Phone システムのダイレクトルーティングでアナログデバイスを使用する方法について説明します。
ms.openlocfilehash: 525e898bd0eafe88d6893249465734d7c33a10b2
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341791"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="f6d76-103">電話システムのダイレクトルーティングでアナログデバイスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="f6d76-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="f6d76-104">この記事では、電話システムダイレクトルーティングでアナログデバイスを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="f6d76-105">アナログデバイスを直接ルーティングに接続するには、アナログテレフォニーアダプター (ATA) を使用する必要があります。このアダプターは、認定セッションボーダーコントローラー (SBC) ベンダーによってサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="f6d76-106">ユーザーがアナログデバイスから通話を発信すると、アナログテレフォニーアダプター (ATA) 経由での信号送信およびメディアフローが SBC に転送されます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="f6d76-107">SBC は、内部ルーティングテーブルに基づいて、通話を Microsoft Teams のエンドポイントに、または PSTN (公衆交換電話網) に送ります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="f6d76-108">デバイスが通話を発信すると、デバイスに対して作成されたルーティングポリシーによって、ルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="f6d76-109">次の図では、2つのチームが + 1425 4XX XX XX と + 1425 5XX XX xx の間の番号を呼び出し、かつ、+ 1425 4XX xx xx とその他の数字との間にある任意の数の PSTN 通話を受け取るように、ダイレクトルーティングが構成されています。 数値の範囲 + 1425 5XX XX XX は、青色のルート (実線) を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![ダイレクトルーティング構成を示す図](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="f6d76-111">例: ダイレクトルーティングでアナログデバイスの使用を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f6d76-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="f6d76-112">ダイレクトルーティングでアナログデバイスの使用を構成するには、アナログのテレフォニーアダプターを SBC に接続し、直接ルーティングを使用するように SBC を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="f6d76-113">この例では、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="f6d76-114">SBC をダイレクトルーティングに接続する</span><span class="sxs-lookup"><span data-stu-id="f6d76-114">Connect the SBC to Direct Routing</span></span>
2. <span data-ttu-id="f6d76-115">PSTN の使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="f6d76-115">Create the PSTN Usage</span></span>
3. <span data-ttu-id="f6d76-116">ボイスルートを作成して、PSTN 使用量と関連付ける</span><span class="sxs-lookup"><span data-stu-id="f6d76-116">Create a voice route and associate it with the PSTN Usage</span></span>
4. <span data-ttu-id="f6d76-117">ボイスルートを PSTN 使用量に割り当てる</span><span class="sxs-lookup"><span data-stu-id="f6d76-117">Assign the voice route to the PSTN Usage</span></span>
5. <span data-ttu-id="f6d76-118">オンラインユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="f6d76-118">Enable the online user</span></span>
6. <span data-ttu-id="f6d76-119">ユーザーに音声ルートポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f6d76-119">Assign the voice route policy to the user</span></span>
7. <span data-ttu-id="f6d76-120">アナログデバイスのボイスルートを作成する</span><span class="sxs-lookup"><span data-stu-id="f6d76-120">Create a voice route for an analog device</span></span>

<span data-ttu-id="f6d76-121">ATA に ATA を接続して SBC を構成する方法については、「SBC 製造元構成ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6d76-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="f6d76-122">AudioCodes 構成の文書化</span><span class="sxs-lookup"><span data-stu-id="f6d76-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="f6d76-123">手順1</span><span class="sxs-lookup"><span data-stu-id="f6d76-123">Step 1.</span></span>  <span data-ttu-id="f6d76-124">SBC をダイレクトルーティングに接続する</span><span class="sxs-lookup"><span data-stu-id="f6d76-124">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="f6d76-125">次のコマンドは、SBC 接続を次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-125">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="f6d76-126">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6d76-126">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="f6d76-127">シグナリングポート5068</span><span class="sxs-lookup"><span data-stu-id="f6d76-127">Signaling port 5068</span></span>
- <span data-ttu-id="f6d76-128">メディアバイパスモード</span><span class="sxs-lookup"><span data-stu-id="f6d76-128">Media bypass mode</span></span>
- <span data-ttu-id="f6d76-129">SBC に転送された通話履歴情報</span><span class="sxs-lookup"><span data-stu-id="f6d76-129">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="f6d76-130">呼び出しと共に転送される P-Id (PAI) ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f6d76-130">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="f6d76-131">手順 2: PSTN の使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="f6d76-131">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="f6d76-132">次のコマンドでは、空の PSTN の使用状況が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-132">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="f6d76-133">オンラインの PSTN 使用状況は、通話承認に使用される文字列値です。</span><span class="sxs-lookup"><span data-stu-id="f6d76-133">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="f6d76-134">オンラインの PSTN 使用により、オンラインボイスポリシーがルートにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-134">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="f6d76-135">この例では、使用できる PSTN の現在のリストに "Interop" という文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-135">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="f6d76-136">手順 3: ボイスルートを作成して、それを PSTN 使用のために関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-136">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="f6d76-137">このコマンドは、番号範囲 + 1425 XXX XX XX の id "アナログ相互運用" を使って、新しいオンラインボイスルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-137">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="f6d76-138">この音声ルートは、オンラインゲートウェイのリストに適用され、オンラインの PSTN 使用状況 "Interop" と関連付けられます。 sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6d76-138">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="f6d76-139">ボイスルートには、特定のボイスルートを通じてルーティングされる電話番号を特定する正規表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6d76-139">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="f6d76-140">手順 4: ボイスルートを PSTN 使用量に割り当てる:</span><span class="sxs-lookup"><span data-stu-id="f6d76-140">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="f6d76-141">このコマンドは、Id が "AnalogInteropPolicy" のオンラインのユーザーごとのボイスルーティングポリシーを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-141">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="f6d76-142">このポリシーには、"Interop" という1つのオンライン PSTN 使用法が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="f6d76-142">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="f6d76-143">手順 5: オンラインユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="f6d76-143">Step 5: Enable the online user</span></span>

<span data-ttu-id="f6d76-144">このコマンドは、Id exampleuser@contoso.com を持つユーザーアカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="f6d76-144">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="f6d76-145">この場合、アカウントが変更され、有効になっているボイスメールを使用して、このユーザーに番号 + 142億5500万が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-145">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="f6d76-146">このコマンドは、会社のテナントの各 Teams ユーザー (ATA デバイスユーザーを除く) に対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-146">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="f6d76-147">手順 6: ボイスルーティングポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f6d76-147">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="f6d76-148">このコマンドは、ユーザーごとのオンラインボイスルーティングポリシー AnalogInteropPolicy を id exampleuser@contoso.com のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-148">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="f6d76-149">このコマンドは、会社のテナントの各 Teams ユーザー (ATA デバイスユーザーを除く) に対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-149">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="f6d76-150">手順 7: アナログデバイスのボイスルートを作成する</span><span class="sxs-lookup"><span data-stu-id="f6d76-150">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="f6d76-151">このコマンドを実行すると、番号1425範囲が "アナログ-相互運用" という id のオンラインボイスルーティングが作成され、オンラインゲートウェイ sbc.contoso.com のリストにも適用され、オンラインの PSTN 使用状況 "Interop" と関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-151">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="f6d76-152">このコマンドは、適切な電話番号パターンを持つ各アナログデバイスに対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-152">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="f6d76-153">または、前の手順のいずれかを実行しているときに、オンラインボイスルーティングを構成するときに、アナログデバイス用の適切な番号パターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6d76-153">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="f6d76-154">考慮事項</span><span class="sxs-lookup"><span data-stu-id="f6d76-154">Considerations</span></span>

- <span data-ttu-id="f6d76-155">特に注記がない限り、アナログデバイスは、通話を発信するために DTMF 数字を送信できるデバイスです。</span><span class="sxs-lookup"><span data-stu-id="f6d76-155">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="f6d76-156">たとえば、アナログ電話、ファックス機器、オーバーヘッドのポケットベルなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-156">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="f6d76-157">ATA に接続されたアナログ電話は、Teams から検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6d76-157">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="f6d76-158">チームユーザーは、デバイスに関連付けられている電話番号を手動で入力して、そのデバイスに通話を発信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d76-158">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="f6d76-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6d76-159">See also</span></span>

[<span data-ttu-id="f6d76-160">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="f6d76-160">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="f6d76-161">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="f6d76-161">Configure Direct Routing</span></span>](direct-routing-configure.md)
