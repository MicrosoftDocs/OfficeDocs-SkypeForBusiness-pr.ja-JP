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
description: '[Web Apps サーバー Officeの定義] ウィザードでは、展開で新Office Web Apps Server を定義します。 以下の情報を入力します。'
ms.openlocfilehash: 002566fb77539745d1d0023159e9af7852b1ecdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119706"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps サーバーの追加

[Web **Apps サーバー Office定義** ] ウィザードでは、展開で Web Apps サーバー Office新しいアプリケーションを定義します。 以下の情報を入力します。

 **Office Web Apps Server FQDN**: Web Apps Server をホストするサーバーの完全修飾ドメイン名Office入力します。

 **Office Web Apps サーバーの** 検出 URL : Web Apps Server の完全な統一リソース ロケーター (URL) をOfficeします。

> [!TIP]
> Web Apps Server Office **検出 URL** の既定の動作は、次の形式で Office Web Apps Server の FQDN に基づいて URL を作成することです `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 多くの場合、既定の形式を変更する必要はありません。 Web Apps Server と Web Apps Server の検出 URL が異なる必要がある場合Office Office既定の形式を変更する必要がある場合があります。 たとえば、Web Apps サーバー Office境界ネットワークに配置され、場所に基づいて別の URL が作成されます。

 **Office Web Apps Server** が外部ネットワーク (境界/インターネット) に展開されている場合: Office Web Apps Server が内部ファイアウォールの外部 (境界ネットワーク、外部ネットワーク、内部ネットワークと同じではない他のネットワーク 領域など) に配置されている場合は、チェック ボックスをオンにします。

## <a name="see-also"></a>関連項目

[会議のコンポーネンツおよびトポロジ](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)