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
description: Skype for Business Server サービスで E9-1-1 と動作する SNMP アプリケーションをエンタープライズ VoIP。
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804157"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="84e17-103">Skype for Business Server で SNMP アプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="84e17-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="84e17-104">Skype for Business Server サービスで E9-1-1 と動作する SNMP アプリケーションをエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="84e17-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="84e17-105">Skype for Business Server には、場所情報サービスをポートおよびスイッチ情報と MAC アドレスと一致する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するために使用できる標準の Web サービス インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84e17-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="84e17-106">SNMP アプリケーションがインストールされ、場所情報サービスが場所データベースで一致するアプリケーションを検出できない場合、場所情報サービスは、クライアントが提供する MAC アドレスを使用してアプリケーションを自動的に照会します。</span><span class="sxs-lookup"><span data-stu-id="84e17-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="84e17-107">その後、場所情報サービスは、SNMP アプリケーションから返されたポートとスイッチ情報を使用して、場所データベースに再度クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="84e17-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84e17-108">MAC アドレスは、MAC アドレスを実行しているコンピューター Windows 8。</span><span class="sxs-lookup"><span data-stu-id="84e17-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="84e17-109">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="84e17-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="84e17-110">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84e17-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="84e17-111">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="84e17-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="84e17-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="84e17-112">See also</span></span>

[<span data-ttu-id="84e17-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="84e17-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

