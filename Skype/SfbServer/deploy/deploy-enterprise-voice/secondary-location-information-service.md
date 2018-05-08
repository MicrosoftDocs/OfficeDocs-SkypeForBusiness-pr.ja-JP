---
title: Skype for Business Server 2015 でのセカンダリ場所情報サービスの構成
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: ~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。
ms.openlocfilehash: 4eaab1b6dfaae9b1298cce3544d89f8b6724733e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a><span data-ttu-id="b8b54-103">Skype for Business Server 2015 でのセカンダリ場所情報サービスの構成</span><span class="sxs-lookup"><span data-stu-id="b8b54-103">Configure a secondary Location Information service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b8b54-104">~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="b8b54-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="b8b54-105">Skype ビジネス サーバーは、セカンダリ場所ソース (SLS) のデータベースに位置情報サービスを指すように使用できる web サービス インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8b54-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="b8b54-106">SLS データベースに接続する web サービスのインタ フェースは、位置情報サービスの WSDL に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8b54-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="b8b54-107">場所データベースとセカンダリ場所データベースの両方を構成すると、位置情報サービスが、まず、場所データベースにクエリを実行し、一致が見つからなかった場合、場所に要求を送信、クライアントから SLS データベースします。</span><span class="sxs-lookup"><span data-stu-id="b8b54-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="b8b54-108">SLS の場所が存在する場合、位置情報サービスは、クライアントに場所を送信します。</span><span class="sxs-lookup"><span data-stu-id="b8b54-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="b8b54-109">セカンダリ場所データベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="b8b54-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="b8b54-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8b54-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b8b54-111">次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="b8b54-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="b8b54-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8b54-112">See also</span></span>

#### 

[<span data-ttu-id="b8b54-113">セット CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="b8b54-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

