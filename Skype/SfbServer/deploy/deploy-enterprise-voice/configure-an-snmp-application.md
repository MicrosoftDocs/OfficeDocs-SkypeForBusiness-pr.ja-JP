---
title: Skype for Business Server で SNMP アプリケーションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice で E9-1-1 と連携するように SNMP アプリケーションを構成します。
ms.openlocfilehash: fd8db117f590343d3e2f5a0194a0f6d8c3bcfb39
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768140"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="494f2-103">Skype for Business Server で SNMP アプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="494f2-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="494f2-104">Skype for Business Server Enterprise Voice で E9-1-1 と連携するように SNMP アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="494f2-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="494f2-105">Skype for Business Server には標準の web サービスインターフェイスが含まれています。これを使用すると、場所情報サービスを、MAC アドレスとポートおよびスイッチ情報を照合する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="494f2-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="494f2-106">SNMP アプリケーションがインストールされていて、位置情報サービスが位置情報データベースで一致を見つけることができなかった場合、位置情報サービスは、クライアントから提供された MAC アドレスを使ってアプリケーションを自動的に照会します。</span><span class="sxs-lookup"><span data-stu-id="494f2-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="494f2-107">次に、位置情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用して、位置情報データベースをもう一度照会します。</span><span class="sxs-lookup"><span data-stu-id="494f2-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="494f2-108">MAC アドレスは、Windows 8 を実行しているコンピューターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="494f2-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="494f2-109">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="494f2-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="494f2-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="494f2-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="494f2-111">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="494f2-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="494f2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="494f2-112">See also</span></span>

[<span data-ttu-id="494f2-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="494f2-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

