---
title: Skype for Business Server でセカンダリの場所情報サービスを構成する
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Skype for Business Server サービスで E9-1-1 のセカンダリロケーション ソース (SLS) データベースをエンタープライズ VoIP。
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830647"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="f4e7a-103">Skype for Business Server でセカンダリの場所情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="f4e7a-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="f4e7a-104">Skype for Business Server サービスで E9-1-1 のセカンダリロケーション ソース (SLS) データベースをエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="f4e7a-105">Skype for Business Server は、場所情報サービスがセカンダリロケーション ソース (SLS) データベースを指す Web サービス インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="f4e7a-106">SLS データベースに接続する Web サービス インターフェイスは、場所情報サービス WSDL に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="f4e7a-107">場所データベースとセカンダリ場所データベースの両方が構成されている場合、場所情報サービスは最初に場所データベースを照会し、一致が見つからない場合は、場所の要求をクライアントから SLS データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="f4e7a-108">場所が SLS に存在する場合、場所情報サービスはその場所をクライアントに返送します。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="f4e7a-109">セカンダリ場所データベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="f4e7a-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="f4e7a-110">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f4e7a-111">次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="f4e7a-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="f4e7a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4e7a-112">See also</span></span>

[<span data-ttu-id="f4e7a-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4e7a-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

