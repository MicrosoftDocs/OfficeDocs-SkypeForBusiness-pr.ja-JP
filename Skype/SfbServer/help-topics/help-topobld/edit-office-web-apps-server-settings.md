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
# <a name="edit-office-web-apps-server-settings"></a>Office Web Apps サーバーの設定を編集する

構成されている Office の Web アプリケーション サーバーのプロパティを編集するとします。 編集できるプロパティは次のとおりです。

 **Office Web アプリケーション サーバーの FQDN**: このプロパティは、Office Web アプリケーション サーバーの完全修飾ドメイン名を定義し、ドメイン ネーム システム (DNS) ホストの A または AAAA (IPv6 が使用されている) 場合に一致する必要がありますレコードです。

 **Office Web アプリケーション サーバーの検出 URL**: Office Web アプリケーション サーバーへのクライアント アクセスの統一リソース ロケーター (URL)、別のネットワーク ゾーンの内部ネットワーク以外のサーバーが配置されている場合既定値からこのアドレスを編集する必要があります、展開します。

このサーバーの展開先が境界ネットワークであるか、または内部展開から境界ネットワーク、信頼性の低いネットワーク、およびインターネットを分離する内部ファイアウォールの外にある他のネットワーク ゾーンである場合は、[**Office Web Apps サーバーは外部ネットワークで展開**] チェック ボックスをオンにします。

![Office Web Apps 設定エキスパンダー](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>関連項目

[コンポーネントおよび会議のためのトポロジ](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)