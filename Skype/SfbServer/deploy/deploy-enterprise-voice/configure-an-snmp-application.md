---
title: Skype for Business Server で SNMP アプリケーションを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Skype for Business Server の E9-1-1 で動作する SNMP アプリケーションを構成エンタープライズ VoIP。
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103633"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="8c092-103">Skype for Business Server で SNMP アプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="8c092-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="8c092-104">Skype for Business Server の E9-1-1 で動作する SNMP アプリケーションを構成エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="8c092-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8c092-105">Skype for Business Server には標準的な Web サービス インターフェイスが含まれています。このインターフェイスを使用して、場所情報サービスをポートおよびスイッチ情報と MAC アドレスと一致する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続できます。</span><span class="sxs-lookup"><span data-stu-id="8c092-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="8c092-106">SNMP アプリケーションがインストールされ、位置情報サービスが場所データベース内で一致する検索に失敗した場合、位置情報サービスはクライアントが提供する MAC アドレスを使用してアプリケーションに自動的にクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c092-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="8c092-107">その後、Location Information Service はポートを使用して、SNMP アプリケーションから返される情報を切り替えて、場所データベースに対して再度クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c092-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c092-108">MAC アドレスは、MAC アドレスを実行しているコンピューターではWindows 8。</span><span class="sxs-lookup"><span data-stu-id="8c092-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="8c092-109">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="8c092-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="8c092-110">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8c092-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8c092-111">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="8c092-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="8c092-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c092-112">See also</span></span>

[<span data-ttu-id="8c092-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c092-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)