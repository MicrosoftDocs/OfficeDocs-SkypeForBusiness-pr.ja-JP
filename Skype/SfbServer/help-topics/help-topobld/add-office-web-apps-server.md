---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Web Apps サーバーのOfficeウィザードでは、展開内の Web Apps サーバー Office新しいアプリケーションを定義します。 以下の情報を入力します。
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828597"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps サーバーの追加

Web **Apps サーバーのOfficeウィザードでは** 、展開内の Web Apps サーバー Office新しいアプリケーションを定義します。 以下の情報を入力します。

 **Office Web Apps サーバーの FQDN**: Web Apps サーバーをホストするサーバーの完全修飾ドメイン名Office入力します。

 **Office Web Apps サーバーの検出 URL**: Web Apps サーバーの完全な URL (uniform resource locator) Office入力します。

> [!TIP]
> **Office Web Apps サーバー** 検出 URL の既定の動作では、次の形式で Office Web Apps サーバーの FQDN に基づいて URL を作成します `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 多くの場合、既定の形式を変更する必要はありません。 Web Apps サーバーと Office Web Apps サーバーの検出 URL が異なる必要Office場合は、既定の形式を変更する必要があります。 たとえば、Office Web Apps サーバーは境界ネットワークに配置され、その場所に基づいて異なる URL を持つ場合があります。

 Office Web Apps サーバーが外部ネットワーク **(境界ネットワーク/インターネット)** に展開されている場合: Office Web Apps サーバーが内部ファイアウォールの外側 (境界ネットワーク、外部ネットワーク、または内部ネットワークと同じではないその他のネットワーク ゾーンなど) にある場合は、このチェック ボックスをオンにします。

## <a name="see-also"></a>関連項目

[会議のコンポーネンツおよびトポロジ](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
