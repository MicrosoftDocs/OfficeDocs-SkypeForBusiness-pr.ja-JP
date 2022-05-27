---
title: -Roll in Set-CsCertificateを使用してSkype for Business Serverで AV 証明書と OAuth 証明書をステージングする
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '概要: Skype for Business Serverの AV 証明書と OAuth 証明書をステージングします。'
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674609"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>-Roll in Set-CsCertificateを使用してSkype for Business Serverで AV 証明書と OAuth 証明書をステージングする

**概要：** Skype for Business Serverの AV 証明書と OAuth 証明書をステージングします。

オーディオ/ビデオ (A/V) 通信は、Skype for Business Serverの重要なコンポーネントです。 アプリケーション共有や音声会議やビデオ会議などの機能は、A/V Edge サービス (特に A/V 認証サービス) に割り当てられた証明書に依存します。

> [!IMPORTANT]
> この新機能は、A/V Edge サービスと OAuthTokenIssuer 証明書で機能するように設計されています。 その他の証明書の種類は、A/V Edge サービスと OAuth 証明書の種類と共にプロビジョニングできますが、A/V Edge サービス証明書が行う共存動作の恩恵を受けられません。

Skype for Business Server証明書の管理に使用される Skype for Business Server Management Shell PowerShell コマンドレットは、A/V Edge サービス証明書を AudioVideoAuthentication 証明書の種類、OAuthServer 証明書を typeOAuthTokenIssuer と呼びます。 このトピックの残りの部分では、証明書を一意に識別するために、同じ識別子の種類である AudioVideoAuthentication とOAuthTokenIssuer によって参照されます。

A/V 認証サービスは、クライアントおよびその他の A/V コンシューマーによって使用されるトークンの発行を担当します。 トークンは証明書の属性から生成され、証明書の有効期限が切れると、接続が失われ、新しい証明書によって生成された新しいトークンに再参加する必要があります。 Skype for Business Serverの新機能により、古い証明書が期限切れになり、両方の証明書が一定期間機能し続けられるようにする前に新しい証明書をステージングする機能という、この問題が軽減されます。 この機能では、Set-CsCertificate Skype for Business Server Management Shell コマンドレットの更新された機能が使用されます。 既存のパラメーター -EffectiveDate を持つ新しいパラメーター -Roll は、新しい AudioVideoAuthentication 証明書を証明書ストアに配置します。 以前の AudioVideoAuthentication 証明書は、発行されたトークンを検証するために残ります。 新しい AudioVideoAuthentication 証明書の配置以降、次の一連のイベントが発生します。

> [!TIP]
> Skype for Business Server Management Shell コマンドレットを使用して証明書を管理すると、エッジ サーバー上で目的ごとに個別の証明書を要求できます。 Skype for Business Server展開ウィザードで証明書ウィザードを使用すると、証明書の作成に役立ちますが、通常は **既定** の種類で、エッジ サーバーで使用されるすべての証明書を 1 つの証明書に結合します。 ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。 既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。 証明書の有効期限が切れたときにインスタント メッセージング会話に関与する (たとえば) ユーザーは、Access Edge サービスに関連付けられている新しい証明書を使用するためにログアウトしてログインし直す必要があります。 同様の動作は、Web 会議エッジ サービスを使用して Web 会議に関与するユーザーに対して発生します。 OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。 証明書を 1 か所で作成および管理すると、証明書は他のすべてのサーバーの Central Management ストアに保存されます。

Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。 -Roll パラメーターは重要ですが、本質的には単一の目的です。 パラメーターとして定義すると、-EffectiveDate によって証明書が有効に定義されるときに、-Type (AudioVideoAuthentication や OAuthTokenIssuer など) によって定義される影響を受ける証明書に関する情報を提供することをSet-CsCertificateに伝えています。

 **-Roll**: -Roll パラメーターは必須であり、依存関係と共に指定する必要があります。 どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。

 **-EffectiveDate**: パラメーター -EffectiveDate は、新しい証明書が現在の証明書と共にアクティブになるタイミングを定義します。 EffectiveDate は、現在の証明書の有効期限に近い場合や、より長い期間を指定できます。 AudioVideoAuthentication 証明書に推奨される最小 -EffectiveDate は 8 時間です。これは、AudioVideoAuthentication 証明書を使用して発行された AV Edge サービス トークンの既定のトークン有効期間です。

OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。

 **-Thumbprint**: 拇印は証明書の属性で、証明書ごとに一意となります。 -Thumbprint パラメーターは、Set-CsCertificate コマンドレットのアクションの影響を受ける証明書を識別するために使用されます。

 **-Type**: -Type パラメーターは、1 つの証明書の使用法の種類または証明書の使用の種類のコンマ区切りの一覧を受け入れます。 証明書の種類は、コマンドレットとサーバーに対して証明書の目的を識別する種類です。 たとえば、「AudioVideoAuthentication」と入力すると、A/V Edge サービスと AV 認証サービスで使用されます。 別の種類の証明書を同時にステージングしてプロビジョニングする場合は、証明書に必要な最短の有効なリード タイムを考慮する必要があります。 たとえば、AudioVideoAuthentication と OAuthTokenIssuer 型の証明書をステージングする必要があります。 最小の -EffectiveDate は、2 つの証明書のうち、24 時間の最小リード タイムを持つ OAuthTokenIssuer の方が大きい必要があります。 潜在時間が 24 時間の AudioVideoAuthentication 証明書をステージングしない場合は、要件に合った EffectiveDate を使用して個別にステージングします。

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll パラメーターと -EffectiveDate パラメーターを使用して A/V Edge サービス証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2. A/V Edge サービス上の既存の証明書のエクスポート可能な秘密キーを使用して、更新または新しい AudioVideoAuthentication 証明書を要求します。

3. 新しい AudioVideoAuthentication 証明書を、エッジ サーバーとプール内の他のすべてのエッジ サーバーにインポートします (プールがデプロイされている場合)。

4. Set-CsCertificate コマンドレットを使用してインポートされた証明書を構成し、-EffectiveDate パラメーターで -Roll パラメーターを使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。 これにより、証明書をアクティブに設定する必要があり、-EffectiveDate \<string\>: "7/22/2015 6:00:00 AM" になります。

   > [!IMPORTANT]
   > エッジ プールの場合、すべてのクライアントトークンとコンシューマー トークンが新しい証明書を使用して更新される前に古い証明書が期限切れになる可能性があるため、最初の証明書の -EffectiveDate パラメーターによって定義された日付と時刻で展開およびプロビジョニングされたすべての AudioVideoAuthentication 証明書がデプロイされている必要があります。

   Roll パラメーターと -EffectiveTime パラメーターを使用したSet-CsCertificate コマンド:

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   Set-CsCertificate コマンドの例を次に示します。

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate は、サーバーのリージョンと言語の設定に合わせて書式設定する必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。

Set-CsCertificate、-Roll、および -EffectiveDate が新しい AudioVideoAuthentication トークンを発行するための新しい証明書をステージングするために使用するプロセスをさらに理解するために、コンシューマーが使用している AudioVideoAuthentication を検証するために既存の証明書を引き続き使用するには、視覚的なタイムラインがプロセスを理解する効果的な手段です。 次の例では、管理者は、A/V Edge サービス証明書が 2015 年 7 月 22 日午後 2 時に期限切れになると判断します。 新しい証明書を要求して受信し、プール内の各エッジ サーバーにインポートします。 2015 年 7 月 22 日午前 2 時に、新しい証明書の拇印文字列に等しい -Roll、-Thumbprint、および -EffectiveTime を 2015 年 6 月 22 日午前 6 時 00 分に設定して、Get-CsCertificateの実行を開始します。 各エッジ サーバーでこのコマンドを実行します。

![Roll パラメーターと EffectiveDate パラメーターを使用します。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|吹き出し|ステージ|
|:-----|:-----|
|1|開始: 2015 年 7 月 22 日午前 12:00:00  <br/> 現在の AudioVideoAuthentication 証明書は、2015 年 7 月 22 日午後 2 時に期限切れになる予定です。 これは、証明書の有効期限が切れたタイムスタンプによって決まります。 既存の証明書の有効期限が切れる前に、証明書の置き換えとロールオーバーを計画して、8 時間の重複 (既定のトークン有効期間) を考慮します。 この例では、午前 2:00:00 のリード タイムを使用して、管理者が有効時間の午前 6:00:00 より前に新しい証明書を配置してプロビジョニングするのに十分な時間を確保します。|
|2|2015 年 7 月 22 日 2:00:00 AM - 7/22/2015 5:59:59 AM  <br/> Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate を使用して、有効時間が 6:00:00 AM のエッジ サーバーに証明書を設定します (この例では 4 時間のリード タイムですが、長くすることができます)。 \<datetime string of the effective time for new certificate\>|
|3|2015 年 7 月 22 日 6:00 AM - 7/22/2015 2:00 PM  <br/> トークンを検証するために、最初に新しい証明書が試行され、新しい証明書でトークンの検証に失敗した場合は、古い証明書が試行されます。 このプロセスは、8 時間 (既定のトークン有効期間) の重複期間中にすべてのトークンに使用されます。|
|4|終了: 2015 年 7 月 22 日 2:00:01 PM  <br/> 古い証明書の有効期限が切れ、新しい証明書が引き継がれました。 古い証明書は、Remove-CsCertificate -Type \<certificate usage type\> -Previous で安全に削除できます|

有効時間 (2015 年 7 月 22 日午前 6 時 00 分) に達すると、すべての新しいトークンが新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた後 (2015 年 7 月 22 日午後 2 時 00 分)、トークンは新しい証明書によってのみ検証されます。 以前の証明書は、-Previous パラメーターを持つRemove-CsCertificateコマンドレットを使用して安全に削除できます。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll パラメーターと -EffectiveDate パラメーターを使用して OAuthTokenIssuer 証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2. フロントエンド サーバー上の既存の証明書のエクスポート可能な秘密キーを使用して、更新または新しい OAuthTokenIssuer 証明書を要求します。

3. プール内のフロント エンド サーバーに新しい OAuthTokenIssuer 証明書をインポートします (プールがデプロイされている場合)。 OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新および書き換うだけで十分です。 フロント エンド サーバーは例として使用されます。

4. Set-CsCertificate コマンドレットを使用してインポートされた証明書を構成し、-EffectiveDate パラメーターで -Roll パラメーターを使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。

    Roll パラメーターと -EffectiveTime パラメーターを使用したSet-CsCertificate コマンド:

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

Set-CsCertificate コマンドの例を次に示します。

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> EffectiveDate は、サーバーのリージョンと言語の設定に合わせて書式設定する必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。

有効時間 (2015 年 7 月 21 日午前 1 時 00 分:00 分) に達すると、すべての新しいトークンが新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた後 (2015 年 7 月 22 日午後 2 時 00 分)、トークンは新しい証明書によってのみ検証されます。 以前の証明書は、-Previous パラメーターを持つRemove-CsCertificateコマンドレットを使用して安全に削除できます。

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>関連項目

[Skype for Business Serverでサーバー間認証 (OAuth) とパートナー アプリケーションを管理する](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
