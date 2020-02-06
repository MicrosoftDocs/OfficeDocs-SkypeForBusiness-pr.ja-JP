---
title: Web サービス設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジビルダーでは、内部と外部の両方の web サービスで使用されるポート設定を変更できます。 さらに、ドメインネームシステム (DNS) 負荷分散を展開している場合は、トポロジビルダーを使用して、そのプールのすべてのサーバーの物理 IP アドレスに解決されるプールの完全修飾ドメイン名 (FQDN) を構成することもできます。
ms.openlocfilehash: e2460305199d1d626e44e5476adc6baf618ebe89
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795228"
---
# <a name="web-services-settings-expander"></a>Web サービス設定エキスパンダー
 
トポロジビルダーでは、内部と外部の両方の web サービスで使用されるポート設定を変更できます。 さらに、ドメインネームシステム (DNS) 負荷分散を展開している場合は、トポロジビルダーを使用して、そのプールのすべてのサーバーの物理 IP アドレスに解決されるプールの完全修飾ドメイン名 (FQDN) を構成することもできます。
  
### <a name="editing-web-services-settings"></a>Web サービス設定の編集

1. 該当する Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールを選択し、[**プロパティの編集**] をクリックします。
    
2. [**プロパティの編集**] ダイアログ ボックスで、[**Web サービス**] タブをクリックします。
    
    > [!CAUTION]
    > フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。 たとえば、フロントエンドサーバーの外部 Web サービス FQDN を**pool01.contoso.com**として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して**pool01.contoso.com**を使用することはできません。 ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。 自動定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。
  
3. Enterprise Edition プールのプロパティを編集する場合は、[**FQDN の上書き**] を選択できます。 このオプションは、ドメイン ネーム システム (DNS) 負荷分散を使用する場合にのみ選択してください。 DNS 負荷分散を使用する場合は、[**FQDN の上書き**] を選択してから、テキスト ボックスにプール内のすべてのサーバーの物理 IP アドレスに解決するそのプールの完全修飾ドメイン名 (FQDN) を入力します。 DNS 負荷分散を使用しない場合、および [**FQDN の上書き**] を選択しない場合は、内部 Web サービスの FQDN を変更できません。 内部 web サービス FQDN は、内部ユーザーが Skype for Business Server に接続するために使用する URL です。
    
4. オプションとして、[**リッスン ポート**] および [**公開ポート**] に、新しい HTTP、HTTPS、または HTTP と HTTPS の値を入力します。リッスン ポートは、着信側のセッション開始プロトコル (SIP) トラフィックをリッスンするためにインターネット インフォメーション サービス (IIS) で使用されるポートです。公開ポートは、ロード バランサーまたはリバース プロキシ サーバーで構成されるポートで、やはり着信 SIP トラフィックをリッスンするために使用されます。既定では、HTTP リッスン ポートと HTTP 公開ポートの両方がポート 80 に設定されており、対応する HTTPS ポートは両方とも 443 に設定されます。2 つの HTTP 公開ポートの既定値は 8080 で、対応する HTTPS ポートは 4443 に設定されます。
    
5. [**OK**] をクリックします。
    
内部 FQDN またはいずれかのリッスン ポートの割り当てを変更する場合は、変更を有効にするために、プール内のすべてのサーバーでローカル セットアップを再実行する必要があります。
  

