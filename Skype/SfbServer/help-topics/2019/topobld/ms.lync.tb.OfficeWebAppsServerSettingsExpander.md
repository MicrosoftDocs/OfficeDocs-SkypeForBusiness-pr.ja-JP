---
title: Office Web Apps サーバーの設定を編集する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: 構成済みの Office Web Apps サーバーのプロパティを編集します。 編集できるプロパティは次のとおりです。
ms.openlocfilehash: 61110a5db604d6fb3cbe89c0da428428820917a2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303278"
---
# <a name="edit-office-web-apps-server-settings"></a><span data-ttu-id="5aaa3-104">Office Web Apps サーバーの設定を編集する</span><span class="sxs-lookup"><span data-stu-id="5aaa3-104">Edit Office Web Apps Server Settings</span></span>

<span data-ttu-id="5aaa3-105">構成済みの Office Web Apps サーバーのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="5aaa3-105">You edit the properties of the configured Office Web Apps Server.</span></span> <span data-ttu-id="5aaa3-106">編集できるプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5aaa3-106">The following properties are available to edit:</span></span>

 <span data-ttu-id="5aaa3-107">**Office Web Apps サーバー FQDN**: このプロパティは、Office Web apps サーバーの完全修飾ドメイン名を定義し、ドメインネームシステム (DNS) のホスト a または AAAA (IPv6 が使用されている場合) レコードと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aaa3-107">**Office Web Apps Server FQDN**: This property defines the fully qualified domain name of the Office Web Apps Server and should match a domain name system (DNS) host A or AAAA (if IPv6 is being used) record.</span></span>

 <span data-ttu-id="5aaa3-108">**Office Web Apps サーバー検出 url**: Office Web apps サーバーへのクライアントアクセスのための uniform resource LOCATOR (url)。サーバーが内部ネットワーク以外の別のネットワークゾーンに配置されている場合は、既定のアドレスを変更することが必要になることがあります。デプロイメント.</span><span class="sxs-lookup"><span data-stu-id="5aaa3-108">**Office Web Apps Server discovery URL**: The uniform resource locator (URL) for client access to the Office Web Apps Server, you may need to edit this address from its default if the server is placed in another network zone other than the internal network for your deployment.</span></span>

<span data-ttu-id="5aaa3-109">このサーバーの展開先が境界ネットワークであるか、または内部展開から境界ネットワーク、信頼性の低いネットワーク、およびインターネットを分離する内部ファイアウォールの外にある他のネットワーク ゾーンである場合は、[**Office Web Apps サーバーは外部ネットワークで展開**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5aaa3-109">Select the check box **Office Web Apps Server is deployed in an external network** if this server is deployed in your perimeter network or other network zone that is outside of your internal firewall separating the perimeter network, less trusted networks, and the Internet from your internal deployment.</span></span>

![Office Web Apps 設定エキスパンダー](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="5aaa3-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5aaa3-111">See also</span></span>

[<span data-ttu-id="5aaa3-112">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="5aaa3-112">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
