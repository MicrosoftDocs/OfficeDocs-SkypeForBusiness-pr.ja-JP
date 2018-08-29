---
title: Office Web Apps サーバーの設定を編集する
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/19/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 構成されている Office の Web アプリケーション サーバーのプロパティを編集するとします。 編集できるプロパティは次のとおりです。
ms.openlocfilehash: 321f159de58779874597588a88a6bb461918d27c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263479"
---
# <a name="edit-office-web-apps-server-settings"></a><span data-ttu-id="07e56-104">Office Web Apps サーバーの設定を編集する</span><span class="sxs-lookup"><span data-stu-id="07e56-104">Edit Office Web Apps Server Settings</span></span>

<span data-ttu-id="07e56-105">構成されている Office の Web アプリケーション サーバーのプロパティを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="07e56-105">You edit the properties of the configured Office Web Apps Server.</span></span> <span data-ttu-id="07e56-106">編集できるプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07e56-106">The following properties are available to edit:</span></span>

 <span data-ttu-id="07e56-107">**Office Web アプリケーション サーバーの FQDN**: このプロパティは、Office Web アプリケーション サーバーの完全修飾ドメイン名を定義し、ドメイン ネーム システム (DNS) ホストの A または AAAA (IPv6 が使用されている) 場合に一致する必要がありますレコードです。</span><span class="sxs-lookup"><span data-stu-id="07e56-107">**Office Web Apps Server FQDN**: This property defines the fully qualified domain name of the Office Web Apps Server and should match a domain name system (DNS) host A or AAAA (if IPv6 is being used) record.</span></span>

 <span data-ttu-id="07e56-108">**Office Web アプリケーション サーバーの検出 URL**: Office Web アプリケーション サーバーへのクライアント アクセスの統一リソース ロケーター (URL)、別のネットワーク ゾーンの内部ネットワーク以外のサーバーが配置されている場合既定値からこのアドレスを編集する必要があります、展開します。</span><span class="sxs-lookup"><span data-stu-id="07e56-108">**Office Web Apps Server discovery URL**: The uniform resource locator (URL) for client access to the Office Web Apps Server, you may need to edit this address from its default if the server is placed in another network zone other than the internal network for your deployment.</span></span>

<span data-ttu-id="07e56-109">このサーバーの展開先が境界ネットワークであるか、または内部展開から境界ネットワーク、信頼性の低いネットワーク、およびインターネットを分離する内部ファイアウォールの外にある他のネットワーク ゾーンである場合は、[**Office Web Apps サーバーは外部ネットワークで展開**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="07e56-109">Select the check box **Office Web Apps Server is deployed in an external network** if this server is deployed in your perimeter network or other network zone that is outside of your internal firewall separating the perimeter network, less trusted networks, and the Internet from your internal deployment.</span></span>

![Office Web Apps 設定エキスパンダー](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="07e56-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="07e56-111">See also</span></span>

[<span data-ttu-id="07e56-112">コンポーネントおよび会議のためのトポロジ</span><span class="sxs-lookup"><span data-stu-id="07e56-112">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)