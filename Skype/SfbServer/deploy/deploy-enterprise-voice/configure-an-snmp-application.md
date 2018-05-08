---
title: Skype for Business Server 2015 での SNMP アプリケーションの構成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。
ms.openlocfilehash: 4d864d8617f679867e514f3cc74ae4fe0201a989
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a><span data-ttu-id="3bff0-103">Skype for Business Server 2015 での SNMP アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="3bff0-103">Configure an SNMP application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3bff0-104">ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3bff0-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="3bff0-105">Skype ビジネス サーバー用には、位置情報サービスをポートを MAC アドレスに一致して、スイッチの情報が簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するために使用できる標準的な web サービス インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bff0-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="3bff0-106">SNMP アプリケーションがインストールされている位置情報サービスは、場所データベース内の一致を検索するのには障害が発生した場合は、位置情報サービスは自動的にクライアントから提供された MAC アドレスを使用してアプリケーションを照会します。</span><span class="sxs-lookup"><span data-stu-id="3bff0-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="3bff0-107">位置情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用してもう一度場所データベースにクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3bff0-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bff0-108">MAC アドレスは、Windows 8 を実行するコンピューターで使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="3bff0-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="3bff0-109">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="3bff0-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="3bff0-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bff0-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3bff0-111">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="3bff0-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="3bff0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bff0-112">See also</span></span>

#### 

[<span data-ttu-id="3bff0-113">セット CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="3bff0-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

