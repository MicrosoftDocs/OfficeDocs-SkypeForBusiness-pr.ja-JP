---
title: Office Web Apps サーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 新しいオフィス ・ Web アプリケーション サーバーの定義ウィザードでは、展開の新しいオフィスの Web アプリケーション サーバーを定義します。 以下の情報を入力します。
ms.openlocfilehash: 6496dddbba50dccbde041133de90f3346ce1a850
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897773"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps サーバーを追加する

**新しいオフィス ・ Web アプリケーション サーバーの定義**ウィザードでは、展開の新しいオフィスの Web アプリケーション サーバーを定義します。 以下の情報を入力します。

 **Office Web アプリケーション サーバーの FQDN**: Office の Web アプリケーション サーバーをホストするサーバーの完全修飾ドメイン名を入力します。

 **Office Web アプリケーション サーバーの検出 URL**: Office Web アプリケーション サーバーの完全な統一リソース ロケーター (URL) を入力します。

> [!TIP]
> 形式で Office Web アプリケーション サーバーの FQDN に基づいて URL を作成するのには、 **Office Web アプリケーション サーバーの検出 URL**の既定の動作: `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 多くの場合、既定の形式を変更する必要はありません。 Office Web アプリケーション サーバーと Web アプリケーション サーバーの検出 URL を別にする必要があることは、既定の書式を変更する必要があります。 などの Office Web アプリケーション サーバーは境界ネットワークに配置され、場所に基づいて別の URL があります。

 **Office Web アプリケーション サーバーが外部ネットワーク (つまり、境界領域またはインターネット) に配置**します] チェック ボックスをオンに、Office Web アプリケーション サーバーが境界ネットワーク、外部ネットワーク、またはその他のネットワーク ゾーンなど、内部のファイアウォールの外側に配置されている場合。内部ネットワークと同じです。

## <a name="see-also"></a>関連項目

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
