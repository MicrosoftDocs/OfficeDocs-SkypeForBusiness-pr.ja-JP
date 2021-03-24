---
title: Office Web Apps サーバーの設定を編集する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 構成されている Web Apps Server のプロパティOffice編集します。 編集できるプロパティは次のとおりです。
ms.openlocfilehash: e9f4a188c5cb58be685db4ea44157f2897ebe5ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095541"
---
# <a name="edit-office-web-apps-server-settings"></a>Office Web Apps サーバーの設定の編集

構成されている Web Apps Server のプロパティOffice編集します。 編集できるプロパティは次のとおりです。

 **Office Web Apps Server FQDN**: このプロパティは、Office Web Apps Server の完全修飾ドメイン名を定義し、ドメイン ネーム システム (DNS) ホスト A または AAAA (IPv6 が使用されている場合) レコードと一致する必要があります。

 **Office Web Apps Server** 探索 URL : Office Web Apps Server へのクライアント アクセス用の統一リソース ロケーター (URL) では、展開用の内部ネットワーク以外の別のネットワーク 領域にサーバーが配置されている場合は、既定からこのアドレスを編集する必要があります。

このサーバーの展開先が境界ネットワークであるか、または内部展開から境界ネットワーク、信頼性の低いネットワーク、およびインターネットを分離する内部ファイアウォールの外にある他のネットワーク ゾーンである場合は、[**Office Web Apps サーバーは外部ネットワークで展開**] チェック ボックスをオンにします。

![Office Web アプリ設定エキスパンダー](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>関連項目

[会議のコンポーネンツおよびトポロジ](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)