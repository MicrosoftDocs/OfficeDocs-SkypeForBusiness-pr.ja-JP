---
title: ビジネス用の Skype のコール パーク設定を構成します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Skype ビジネス サーバーのエンタープライズ VoIP のコール パーク設定を変更します。
ms.openlocfilehash: 518cefda9cd6186c8362dea83bb80acb046d441d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019518"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="14a77-103">ビジネス用の Skype のコール パーク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="14a77-103">Configure Call Park settings in Skype for Business</span></span>
 
<span data-ttu-id="14a77-104">Skype ビジネス サーバーのエンタープライズ VoIP のコール パーク設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="14a77-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="14a77-105">コール パークの既定の設定を使用しない場合は、それらをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="14a77-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="14a77-106">コール パーク アプリケーションをインストールすると、グローバル設定は、既定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="14a77-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="14a77-107">グローバルの設定を変更することができ、サイト固有の設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="14a77-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="14a77-108">**新規 CsCpsConfiguration**コマンドレットを使用すると、サイト固有の設定を新しいを作成します。</span><span class="sxs-lookup"><span data-stu-id="14a77-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="14a77-109">**セット CsCpsConfiguration**コマンドレットを使用して、既存の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="14a77-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14a77-110">少なくとも、保留された通話が時間切れになりリングバックが失敗した場合に使用する代替宛先の [**OnTimeoutURI**] オプションは構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14a77-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>
  
<span data-ttu-id="14a77-111">次の設定のいずれかを構成するのにには、**新規 CsCpsConfiguration**コマンドレットまたは**セット CsCpsConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="14a77-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>
  
|<span data-ttu-id="14a77-112">**このオプション:**</span><span class="sxs-lookup"><span data-stu-id="14a77-112">**This option:**</span></span>|<span data-ttu-id="14a77-113">**指定する内容:**</span><span class="sxs-lookup"><span data-stu-id="14a77-113">**Specifies this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14a77-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="14a77-114">**CallPickupTimeoutThreshold**</span></span> <br/> |<span data-ttu-id="14a77-115">通話が保留されてから、呼び出しに応答した電話にかけ直されるまでの経過時間。</span><span class="sxs-lookup"><span data-stu-id="14a77-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="14a77-p102">この値は、hh:mm:ss の形式で入力し、時間、分、および秒を指定する必要があります。最小値は 10 秒、最大値は 10 分です。既定値は 00:01:30 です。</span><span class="sxs-lookup"><span data-stu-id="14a77-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
|<span data-ttu-id="14a77-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="14a77-119">**EnableMusicOnHold**</span></span> <br/> |<span data-ttu-id="14a77-120">通話が保留されている間、発信者に対して音楽を再生するかどうか。</span><span class="sxs-lookup"><span data-stu-id="14a77-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="14a77-p103">値は True または False です。既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="14a77-p103">Values are True or False. The default is True.</span></span>  <br/> |
|<span data-ttu-id="14a77-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="14a77-123">**MaxCallPickupAttempts**</span></span> <br/> |<span data-ttu-id="14a77-p104">保留された通話が [**OnTimeoutURI**] で指定した代替 URI (Uniform Resource Identifier) に転送される前に、応答電話にかけ直される回数。既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="14a77-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/> |
|<span data-ttu-id="14a77-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="14a77-126">**OnTimeoutURI**</span></span> <br/> |<span data-ttu-id="14a77-127">**MaxCallPickupAttempts** を超過した場合に、応答のない保留通話のルーティング先となるユーザーまたは応答グループの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="14a77-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="14a77-p105">値は、文字列 sip: で始まる SIP URI にする必要があります。たとえば、sip:bob@contoso.com などです。既定値は転送アドレスではありません。</span><span class="sxs-lookup"><span data-stu-id="14a77-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/> |
   
### <a name="to-configure-call-park-settings"></a><span data-ttu-id="14a77-131">コール パーク設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="14a77-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="14a77-132">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14a77-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="14a77-133">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14a77-133">Run:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="14a77-134">サイトを識別するのにには、 **Get CsSite**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="14a77-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="14a77-135">詳細については、サーバー管理シェルのビジネス ドキュメントの Skype を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a77-135">For details, see Skype for Business Server Management Shell documentation.</span></span>
  
    <span data-ttu-id="14a77-136">例:</span><span class="sxs-lookup"><span data-stu-id="14a77-136">For example:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="14a77-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="14a77-137">See also</span></span>

[<span data-ttu-id="14a77-138">Skype for Business 2015 でのコール パーク保留音のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="14a77-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="14a77-139">新しい-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="14a77-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="14a77-140">セット CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="14a77-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="14a77-141">Get CsSite</span><span class="sxs-lookup"><span data-stu-id="14a77-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)