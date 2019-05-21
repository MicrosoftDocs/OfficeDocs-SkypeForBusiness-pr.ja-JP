---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: '[新しい Office Web Apps サーバーの定義] ウィザードでは、展開で新しい Office Web Apps サーバーを定義します。 以下の情報を入力します。'
ms.openlocfilehash: f5cf9c686ec7d42db6db15021e28493507f954b5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306165"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps サーバーを追加する

[**新しい Office Web Apps サーバーの定義**] ウィザードでは、展開で新しい Office Web apps サーバーを定義します。 以下の情報を入力します。

 **Office Web Apps サーバー FQDN**: Office Web apps サーバーをホストするサーバーの完全修飾ドメイン名を入力します。

 **Office Web Apps サーバー検出 URL**: Office Web apps サーバーの完全な uniform resource LOCATOR (URL) を入力します。

> [!TIP]
> **Office Web Apps サーバー検出 URL**の既定の動作では、次`https://<FQDN of the Office Web Apps Server/hosting/discovery`の形式の office WEB apps サーバーの FQDN に基づいて url が作成されます。 多くの場合、既定の形式を変更する必要はありません。 Office Web Apps サーバーと Office Web Apps サーバー検出 URL が異なっている必要がある場合は、既定の形式を変更する必要がある場合があります。 たとえば、Office Web Apps サーバーは境界ネットワーク内に配置され、その場所に基づいて異なる URL が設定されます。

 **Office Web Apps サーバーは外部ネットワーク (つまり、境界/インターネット) に展開され**ます。 Office Web apps サーバーが、境界ネットワーク、外部ネットワーク、その他のネットワークゾーンなどの内部ファイアウォールの外側に配置されている場合は、このチェックボックスをオンにします。これは、内部ネットワークとは異なります。

## <a name="see-also"></a>関連項目

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
