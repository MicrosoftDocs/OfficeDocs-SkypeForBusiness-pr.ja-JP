---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: '[新しい Office Web Apps サーバーの定義] ウィザードは、展開に新しい Office Web Apps サーバーを定義します。 以下の情報を入力します。'
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218728"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps サーバーを追加する

[ **新しい Office Web Apps サーバーの定義** ] ウィザードは、展開に新しい Office Web apps サーバーを定義します。 以下の情報を入力します。

 **Office Web Apps サーバーの FQDN**: Office Web apps サーバーをホストするサーバーの完全修飾ドメイン名を入力します。

 **Office Web Apps サーバー検出 url**: Office Web apps サーバーの完全な url (uniform resource locator) を入力します。

> [!TIP]
> **Office Web Apps サーバー検出 url**の既定の動作では、Office Web apps サーバーの FQDN に基づいて url を次の形式で作成し `https://<FQDN of the Office Web Apps Server/hosting/discovery` ます。 多くの場合、既定の形式を変更する必要はありません。 Office Web Apps サーバーと Office Web Apps サーバー検出の URL が異なる場合は、既定の形式を変更する必要がある場合があります。 たとえば、Office Web Apps サーバーは境界ネットワークに配置され、その場所に基づいて異なる URL を持ちます。

 **Office Web Apps サーバーが外部ネットワーク (境界/インターネット) に展開され**ている場合: 境界ネットワーク、外部ネットワーク、内部ネットワークと同じではない他のネットワークゾーンなど、Office Web apps サーバーを内部ファイアウォールの外側に配置する場合は、このチェックボックスをオンにします。

## <a name="see-also"></a>関連項目

[会議のコンポーネンツおよびトポロジ](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
