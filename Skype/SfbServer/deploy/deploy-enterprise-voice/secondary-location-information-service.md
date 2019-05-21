---
title: Skype for Business Server でセカンダリ場所情報サービスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Skype for Business Server Enterprise Voice で、E9 のセカンダリ場所ソース (SLS) データベースを構成します。
ms.openlocfilehash: 0d637b8b2b61526837be2d56b8654f40bc556064
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288534"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="ae507-103">Skype for Business Server でセカンダリ場所情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="ae507-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="ae507-104">Skype for Business Server Enterprise Voice で、E9 のセカンダリ場所ソース (SLS) データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae507-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ae507-105">Skype for Business Server には、位置情報サービスをセカンダリの場所のソース (SLS) データベースにポイントするために使用できる web サービスインターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ae507-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="ae507-106">SLS データベースに接続する web サービスインターフェイスは、位置情報サービスの WSDL に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae507-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="ae507-107">ロケーションデータベースとセカンダリロケーションデータベースの両方が構成されている場合、位置情報サービスは最初に位置情報データベースを照会し、一致が見つからない場合は、クライアントから SLS データベースに位置情報要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="ae507-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="ae507-108">場所が SLS に存在する場合、位置情報サービスはその場所をクライアントに送り返します。</span><span class="sxs-lookup"><span data-stu-id="ae507-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="ae507-109">セカンダリ場所データベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="ae507-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="ae507-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae507-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ae507-111">次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="ae507-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="ae507-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae507-112">See also</span></span>

[<span data-ttu-id="ae507-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ae507-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

