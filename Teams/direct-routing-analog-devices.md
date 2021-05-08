---
title: ダイレクト ルーティング - アナログ デバイスの接続
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
description: この記事では、システム ダイレクト ルーティングでアナログ デバイスを使用するMicrosoft 電話説明します。
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841488"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="4584b-103">ダイレクト ルーティングでアナログ デバイスを使用電話システム方法</span><span class="sxs-lookup"><span data-stu-id="4584b-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="4584b-104">この記事では、ダイレクト ルーティングでアナログ デバイスを使用する電話システム説明します。</span><span class="sxs-lookup"><span data-stu-id="4584b-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="4584b-105">アナログ デバイスをダイレクト ルーティングに接続するには、アナログ テレフォニー アダプター (ATA) を使用する必要があります。このアダプターは認定セッション ボーダー コントローラー (SBC) ベンダーによってサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="4584b-106">ユーザーがアナログ デバイスから呼び出しを行った場合、信号とメディアはアナログ テレフォニー アダプター (ATA) を介して SBC に送信されます。</span><span class="sxs-lookup"><span data-stu-id="4584b-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="4584b-107">SBC は、内部ルーティング テーブルに基づいて、Microsoft Teams エンドポイントまたは公衆交換電話網 (PSTN) に通話を送信します。</span><span class="sxs-lookup"><span data-stu-id="4584b-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="4584b-108">デバイスが呼び出しを行う場合、そのデバイスが使用するルートは、デバイス用に作成されたルーティング ポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4584b-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="4584b-109">次の図では、 直接ルーティングは、+1425 4XX XX XX と +1425 5XX XX XX の間の番号との間の Teams 呼び出しが赤いルート (点線) を受け取る必要があります。また、+1425 4XX XX XX と数字範囲 +1425 5XX XX XX を除く他の番号との間の PSTN 呼び出しは、青色のルート (実線) を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4584b-110">![ダイレクト ルーティングの構成を示す図](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="4584b-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="4584b-111">例: ダイレクト ルーティングを使用してアナログ デバイスの使用を構成する方法</span><span class="sxs-lookup"><span data-stu-id="4584b-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="4584b-112">ダイレクト ルーティングを使用してアナログ デバイスの使用を構成するには、アナログ テレフォニー アダプターを SBC に接続し、ダイレクト ルーティングを使用するために SBC を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="4584b-113">この例では、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4584b-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="4584b-114">Connect SBC からダイレクト ルーティングに接続します。</span><span class="sxs-lookup"><span data-stu-id="4584b-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="4584b-115">PSTN 使用法を作成します。</span><span class="sxs-lookup"><span data-stu-id="4584b-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="4584b-116">音声ルートを作成し、PSTN 使用法に関連付ける。</span><span class="sxs-lookup"><span data-stu-id="4584b-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="4584b-117">PSTN 使用法に音声ルートを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="4584b-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="4584b-118">オンライン ユーザーを有効にする。</span><span class="sxs-lookup"><span data-stu-id="4584b-118">Enable the online user.</span></span>
6. <span data-ttu-id="4584b-119">音声ルート ポリシーをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="4584b-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="4584b-120">アナログ デバイスの音声ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4584b-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="4584b-121">ATA を SBC に接続して SBC を構成する方法については、SBC 製造元の構成ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4584b-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="4584b-122">AudioCodes 構成ドキュメント</span><span class="sxs-lookup"><span data-stu-id="4584b-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="4584b-123">リボンの構成に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="4584b-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="4584b-124">Oracle 構成のドキュメント</span><span class="sxs-lookup"><span data-stu-id="4584b-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="4584b-125">手順 1.</span><span class="sxs-lookup"><span data-stu-id="4584b-125">Step 1.</span></span>  <span data-ttu-id="4584b-126">Connect SBC からダイレクト ルーティングへの接続</span><span class="sxs-lookup"><span data-stu-id="4584b-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="4584b-127">次のコマンドは、次のように SBC 接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="4584b-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="4584b-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4584b-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="4584b-129">信号ポート 5068</span><span class="sxs-lookup"><span data-stu-id="4584b-129">Signaling port 5068</span></span>
- <span data-ttu-id="4584b-130">メディア バイパス モード</span><span class="sxs-lookup"><span data-stu-id="4584b-130">Media bypass mode</span></span>
- <span data-ttu-id="4584b-131">SBC に転送された通話履歴情報</span><span class="sxs-lookup"><span data-stu-id="4584b-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="4584b-132">呼び出しと共に転送される P-Asserted-Identity (ASSERTed-Identity)ヘッダー</span><span class="sxs-lookup"><span data-stu-id="4584b-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="4584b-133">手順 2: PSTN 使用状況を作成する</span><span class="sxs-lookup"><span data-stu-id="4584b-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="4584b-134">次のコマンドでは、空の PSTN 使用法が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4584b-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="4584b-135">オンライン PSTN 使用法は、通話承認に使用される文字列値です。</span><span class="sxs-lookup"><span data-stu-id="4584b-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="4584b-136">オンライン PSTN 使用法は、オンライン音声ポリシーをルートにリンクします。</span><span class="sxs-lookup"><span data-stu-id="4584b-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="4584b-137">この例では、使用可能な PSTN 使用法の現在の一覧に文字列 "Interop" を追加します。</span><span class="sxs-lookup"><span data-stu-id="4584b-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="4584b-138">手順 3: 音声ルートを作成し、PSTN 使用法に関連付ける:</span><span class="sxs-lookup"><span data-stu-id="4584b-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="4584b-139">このコマンドは、番号範囲 +1425 XXX XX XX の ID "analog-interop" を持つ新しいオンライン音声ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4584b-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="4584b-140">音声ルートは、オンライン PSTN 使用法 "Interop" sbc.contoso.com 関連付けるオンライン ゲートウェイの一覧に適用できます。</span><span class="sxs-lookup"><span data-stu-id="4584b-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="4584b-141">音声ルートには、特定の音声ルートを介してルーティングされる電話番号を識別する正規表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4584b-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="4584b-142">手順 4: PSTN 使用法に音声ルートを割り当てる:</span><span class="sxs-lookup"><span data-stu-id="4584b-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="4584b-143">このコマンドは、ID "AnalogInteropPolicy" を使用して、ユーザーごとの新しいオンライン音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4584b-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="4584b-144">このポリシーには、単一のオンライン PSTN 使用法 "Interop" が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4584b-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="4584b-145">手順 5: オンライン ユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="4584b-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="4584b-146">このコマンドは、ID アカウントを使用してユーザー アカウントを変更 exampleuser@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="4584b-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="4584b-147">この場合、VoIP の Microsoft 実装である エンタープライズ VoIP を有効にし、ボイス メールを有効にし、このユーザーに +14255000000 の番号を割り当て、アカウントが変更されます。</span><span class="sxs-lookup"><span data-stu-id="4584b-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="4584b-148">このコマンドは、会社のテナントTeamsユーザー (ATA デバイス ユーザーを除く) ごとに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="4584b-149">手順 6: 音声ルート ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4584b-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="4584b-150">このコマンドは、ユーザーごとのオンライン音声ルーティング ポリシー AnalogInteropPolicy を ID アドレスを持つユーザーに割り当 exampleuser@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="4584b-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="4584b-151">このコマンドは、会社のテナントTeamsユーザー (ATA デバイス ユーザーを除く) ごとに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="4584b-152">手順 7: アナログ デバイスの音声ルートを作成する</span><span class="sxs-lookup"><span data-stu-id="4584b-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="4584b-153">このコマンドは、オンライン ゲートウェイ sbc.contoso.com の一覧に適用できる番号範囲 +1425 4XX XX XX の ID "analog-interop" を持つオンライン音声ルートを作成し、オンライン PSTN 使用法 "Interop" に関連付ける。</span><span class="sxs-lookup"><span data-stu-id="4584b-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="4584b-154">このコマンドは、適切な電話番号パターンを持つアナログ デバイスごとに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="4584b-155">または、前のいずれかの手順でオンライン音声ルートを構成する際に、アナログ デバイスの適切な番号パターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4584b-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="4584b-156">考慮事項</span><span class="sxs-lookup"><span data-stu-id="4584b-156">Considerations</span></span>

- <span data-ttu-id="4584b-157">特に注意しない限り、アナログ デバイスは DTMF 数字を送信して通話を発信できる任意のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="4584b-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="4584b-158">たとえば、アナログ電話、FAX マシン、オーバーヘッド ページなどです。</span><span class="sxs-lookup"><span data-stu-id="4584b-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="4584b-159">ATA に接続されているアナログ電話は、デバイスからTeams。</span><span class="sxs-lookup"><span data-stu-id="4584b-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="4584b-160">Teamsユーザーは、デバイスに関連付けられている電話番号を手動で入力して、そのデバイスを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4584b-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="4584b-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="4584b-161">See also</span></span>

[<span data-ttu-id="4584b-162">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="4584b-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="4584b-163">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="4584b-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
