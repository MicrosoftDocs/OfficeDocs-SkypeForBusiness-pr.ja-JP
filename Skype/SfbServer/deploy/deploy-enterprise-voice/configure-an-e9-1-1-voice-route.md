---
title: ビジネス サーバー用の Skype で ~ 9-1-1 のボイス ルートを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: ビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 ボイス ルートを構成します。
ms.openlocfilehash: a465dd40eb79224db4e021a227f46fb0f1f6a129
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890323"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="36f96-103">ビジネス サーバー用の Skype で ~ 9-1-1 のボイス ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="36f96-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="36f96-104">ビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 ボイス ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="36f96-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="36f96-105">E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f96-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="36f96-106">ボイス ルートを作成する方法についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="36f96-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="36f96-107">展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="36f96-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="36f96-108">~ 9-1-1、招待の場所に関する情報を含む、ゲートウェイを介して、緊急通話のルーティングを ~ 9-1-1 のサービス プロバイダーに接続する SIP トランクを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f96-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="36f96-109">これを行うには、True に**セット CsTrunkConfiguration**コマンドレットに EnablePIDFLOSupport フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="36f96-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="36f96-110">EnablePIDFLOSupport の既定値は、False です。</span><span class="sxs-lookup"><span data-stu-id="36f96-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="36f96-111">例:`Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.`フォールバックの公衆は交換電話網 (PSTN) ゲートウェイと緊急位置識別番号 (ELIN) ゲートウェイの受信場所を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36f96-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="36f96-112">E9-1-1 のボイス ルートを構成するには</span><span class="sxs-lookup"><span data-stu-id="36f96-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="36f96-113">RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="36f96-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="36f96-114">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="36f96-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="36f96-115">次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="36f96-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="36f96-116">これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f96-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="36f96-117">展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。</span><span class="sxs-lookup"><span data-stu-id="36f96-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="36f96-118">詳細については、[音声ポリシーを構成する、PSTN 使用法レコード、およびビジネスのための Skype でのボイス ルート](voice-and-pstn.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36f96-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="36f96-119">次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="36f96-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="36f96-120">この番号パターンは、[場所のポリシー] の [**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f96-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="36f96-121">ビジネス用の Skype が追加されるので「+」緊急電話番号には、「+」記号が必要です。</span><span class="sxs-lookup"><span data-stu-id="36f96-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="36f96-122">"Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="36f96-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="36f96-123">次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="36f96-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="36f96-124">必要に応じて、SIP トランク接続では、お勧め ~ 9-1-1 サービス プロバイダーの SIP トランクによって処理されない通話のローカル ルートを作成するのには次のコマンドレットを実行することです。</span><span class="sxs-lookup"><span data-stu-id="36f96-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="36f96-125">このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="36f96-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="36f96-126">次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="36f96-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


