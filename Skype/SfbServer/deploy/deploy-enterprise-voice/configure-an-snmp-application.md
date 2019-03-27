---
title: Skype のビジネス サーバーの SNMP アプリケーションを構成します。
ms.reviewer: ''
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。
ms.openlocfilehash: f45666708b2f5bb3065631bbb4ab38ee88082517
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898600"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="3dccb-103">Skype のビジネス サーバーの SNMP アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3dccb-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="3dccb-104">ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3dccb-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="3dccb-105">Skype ビジネス サーバー用には、位置情報サービスをポートを MAC アドレスに一致して、スイッチの情報が簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するために使用できる標準的な web サービス インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dccb-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="3dccb-106">SNMP アプリケーションがインストールされている位置情報サービスは、場所データベース内の一致を検索するのには障害が発生した場合は、位置情報サービスは自動的にクライアントから提供された MAC アドレスを使用してアプリケーションを照会します。</span><span class="sxs-lookup"><span data-stu-id="3dccb-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="3dccb-107">位置情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用してもう一度場所データベースにクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3dccb-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3dccb-108">MAC アドレスは、Windows 8 を実行するコンピューターで使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="3dccb-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="3dccb-109">SNMP アプリケーションの URL を構成するには</span><span class="sxs-lookup"><span data-stu-id="3dccb-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="3dccb-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3dccb-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3dccb-111">次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="3dccb-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="3dccb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3dccb-112">See also</span></span>

[<span data-ttu-id="3dccb-113">セット CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="3dccb-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

