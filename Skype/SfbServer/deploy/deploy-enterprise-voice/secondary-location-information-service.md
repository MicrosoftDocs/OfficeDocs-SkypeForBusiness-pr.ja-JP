---
title: Skype のビジネス サーバーのセカンダリ場所情報サービスを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: ~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。
ms.openlocfilehash: 047fd1a7dca0c4c2b76d01fd0c5d67230246441e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892294"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="4b18a-103">Skype のビジネス サーバーのセカンダリ場所情報サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="4b18a-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="4b18a-104">~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="4b18a-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="4b18a-105">Skype ビジネス サーバーは、セカンダリ場所ソース (SLS) のデータベースに位置情報サービスを指すように使用できる web サービス インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4b18a-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="4b18a-106">SLS データベースに接続する web サービスのインタ フェースは、位置情報サービスの WSDL に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b18a-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="4b18a-107">場所データベースとセカンダリ場所データベースの両方を構成すると、位置情報サービスが、まず、場所データベースにクエリを実行し、一致が見つからなかった場合、場所に要求を送信、クライアントから SLS データベースします。</span><span class="sxs-lookup"><span data-stu-id="4b18a-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="4b18a-108">SLS の場所が存在する場合、位置情報サービスは、クライアントに場所を送信します。</span><span class="sxs-lookup"><span data-stu-id="4b18a-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="4b18a-109">セカンダリ場所データベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="4b18a-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="4b18a-110">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b18a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4b18a-111">次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="4b18a-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="4b18a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b18a-112">See also</span></span>

[<span data-ttu-id="4b18a-113">セット CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b18a-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

