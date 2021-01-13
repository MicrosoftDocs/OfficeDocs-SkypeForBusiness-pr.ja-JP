---
title: Skype for Business Server で -Roll を使用して、ビデオと OAuth の証明書をSet-CsCertificate
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '概要: Skype for Business Server の AV 証明書と OAuth 証明書をステージします。'
ms.openlocfilehash: a2586e9ebda1bae1605fd6033681b469e6731b8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806557"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Skype for Business Server で -Roll を使用して、ビデオと OAuth の証明書をSet-CsCertificate
 
**概要:** Skype for Business Server の AV 証明書と OAuth 証明書をステージします。
  
音声ビデオ (A/V) 通信は、Skype for Business Server の主要なコンポーネントです。 アプリケーション共有、音声ビデオ会議などの機能は、音声ビデオ エッジ サービス、特に音声ビデオ認証サービスに割り当てられた証明書に依存します。
  
> [!IMPORTANT]
> この新機能は、A/V エッジ サービスと OAuthTokenIssuer 証明書で動作するように設計されています。 その他の種類の証明書は、A/V エッジ サービスと OAuth 証明書の種類と共にプロビジョニングできますが、A/V エッジ サービス証明書が実行する共存動作を利用できません。
  
Skype for Business Server 証明書の管理に使用される Skype for Business Server 管理シェル PowerShell コマンドレットは、音声ビデオ エッジ サービス証明書を AudioVideoAuthentication 証明書の種類として参照し、OAuthServer 証明書を typeOAuthTokenIssuer として参照します。 このトピックの残りの部分では、証明書を一意に識別するために、AudioVideoAuthentication とOAuthTokenIssuer という同じ識別子の種類で参照されます。
  
A/V 認証サービスは、クライアントおよび他の A/V コンシューマーによって使用されるトークンの発行を担当します。 トークンは証明書の属性から生成され、証明書の有効期限が切れると、接続が失われると、新しい証明書によって生成された新しいトークンに再び追加する必要があります。 Skype for Business Server の新機能は、この問題を軽減します。古い証明書の有効期限が切れて、両方の証明書が一期間機能し続ける前に新しい証明書をステージする機能。 この機能では、Skype for Business Server 管理シェル コマンドレットSet-CsCertificate更新された機能を使用します。 新しいパラメーター -Roll と既存のパラメーター -EffectiveDate は、新しい AudioVideoAuthentication 証明書を証明書ストアに配置します。 古い AudioVideoAuthentication 証明書は、発行されたトークンが検証のために残ります。 新しい AudioVideoAuthentication 証明書の配置から始め、次の一連のイベントが発生します。
  
> [!TIP]
> Skype for Business Server 管理シェル コマンドレットを使用して証明書を管理すると、エッジ サーバー上の目的ごとに個別の証明書を要求できます。 Skype for Business Server 展開ウィザードの証明書ウィザードを使用すると、証明書を作成できますが、通常は、エッジサーバーで使用する証明書を 1 つの証明書に結合する既定の種類です。 ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。 既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。 証明書の有効期限が切れた場合にインスタント メッセージングの会話に関与するユーザーは、アクセス エッジ サービスに関連付けられた新しい証明書を利用するためにログアウトしてログインし戻す必要があります。 同様の動作は、Web 会議エッジ サービスを使用する Web 会議に関与するユーザーに対して行われます。 OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。 証明書を 1 か所で作成および管理し、その証明書は他のすべてのサーバーの中央管理ストアに保存されます。
  
Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。 -Roll パラメーターは重要ですが、基本的には単一の目的です。 パラメーターとして定義する場合、-Type で定義される影響を受ける証明書に関する情報を提供する (AudioVideoAuthentication や OAuthTokenIssuer など)、証明書が -EffectiveDate で定義された有効になるときに、Set-CsCertificate に伝える必要があります。
  
 **-Roll**: -Roll パラメーターは必須であり、このパラメーターと共に指定する必要がある依存関係があります。 どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。
  
 **-EffectiveDate**: パラメーター -EffectiveDate は、新しい証明書が現在の証明書と共同アクティブになる時間を定義します。 -EffectiveDate は、現在の証明書の有効期限に近い場合や、期間が長くなる可能性があります。 AudioVideoAuthentication 証明書の推奨最小値 -EffectiveDate は 8 時間です。これは AudioVideoAuthentication 証明書を使用して発行された AV エッジ サービス トークンの既定のトークンの有効期間です。
  
OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。
  
 **-Thumbprint**: 拇印は証明書の属性で、証明書ごとに一意となります。 -Thumbprint パラメーターは、このコマンドレットの操作の影響を受ける証明書を識別Set-CsCertificateします。
  
 **-Type**: -Type パラメーターには、単一の証明書使用法の種類または証明書の使用法の種類のコンマ区切りの一覧を指定できます。 証明書の種類は、コマンドレットと、証明書の目的をサーバーに識別する種類です。 たとえば、音声ビデオ エッジ サービスと AV 認証サービスで使用する AudioVideoAuthentication と入力します。 異なる種類の証明書を同時にステージおよびプロビジョニングする場合は、証明書に必要な最小限の有効リード タイムを考慮する必要があります。 たとえば、AudioVideoAuthentication 型と OAuthTokenIssuer 型の証明書をステージする必要があります。 最小 -EffectiveDate は、2 つの証明書 (この場合は OAuthTokenIssuer) の大きい値である必要があります。この場合、最小リード タイムは 24 時間です。 リード タイムを 24 時間に設定して AudioVideoAuthentication 証明書をステージしない場合は、要件に応じてより多くの EffectiveDate を使用して別にステージします。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll パラメーターと -EffectiveDate パラメーターを使用して、A/V エッジ サービス証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。
    
2. 音声ビデオ エッジ サービス上の既存の証明書のエクスポート可能なプライベート キーを使用して、更新または新しい AudioVideoAuthentication 証明書を要求します。
    
3. 新しい AudioVideoAuthentication 証明書をエッジ サーバーとプール内の他のすべてのエッジ サーバーにインポートします (プールが展開されている場合)。
    
4. Set-CsCertificate コマンドレットを使用してインポートした証明書を構成し、-Roll パラメーターを -EffectiveDate パラメーターと一緒に使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。 これにより、証明書をアクティブに設定する必要がある時間が与え、-EffectiveDate \<string\> : "7/22/2015 6:00:00 AM" になります。 
    
    > [!IMPORTANT]
    > エッジ プールでは、すべての AudioVideoAuthentication 証明書を展開し、新しい証明書を使用してすべてのクライアント トークンとコンシューマー トークンを更新する前に古い証明書の有効期限が切れて音声ビデオ通信が中断される可能性を回避するために、展開された最初の証明書の -EffectiveDate パラメーターで定義された日時で展開およびプロビジョニングする必要があります。 
  
    -Roll Set-CsCertificate -EffectiveTime パラメーターを指定した次のコマンドを実行します。
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Set-CsCertificate コマンドの例を次に示します。
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合わせて書式設定する必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。 
  
Set-CsCertificate、-Roll、および -EffectiveDate が新しい AudioVideoAuthentication トークンを発行するための新しい証明書をステージに入れる一方で、コンシューマーが使用している AudioVideoAuthentication を検証するために既存の証明書を使用するプロセスをさらに理解するには、視覚的なタイムラインがプロセスを理解する効果的な手段です。 次の例では、管理者は、2015 年 7 月 22 日の午後 2:00:00 に、A/V エッジ サービス証明書の有効期限が切れると判断します。 新しい証明書を要求して受け取り、プール内の各エッジ サーバーにインポートします。 2015 年 7 月 22 日の午前 2 時に、-Roll、-Thumbprint が新しい証明書の拇印文字列に等しい -Thumbprint、および -EffectiveTime が 2015 年 7 月 22 日午前 6:00:00 に設定された Get-CsCertificate の実行を開始します。 各エッジ サーバーでこのコマンドを実行します。
  
![Roll パラメーターと EffectiveDate パラメーターを使用する。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**ステージ**|
|:-----|:-----|
|1   <br/> |開始: 2015 年 7 月 22 日午前 12:00:00  <br/> 現在の AudioVideoAuthentication 証明書は、2015 年 7 月 22 日午後 2:00 に期限が切れる予定です。 これは、証明書の有効期限タイム スタンプによって決定されます。 既存の証明書が有効期限に達する前に、8 時間の重複 (既定のトークンの有効期間) を考慮して、証明書の交換とロールオーバーを計画します。 この例では、午前 2:00:00 のリード タイムを使用して、管理者が有効時間の 6:00:00 AM の前に新しい証明書を配置してプロビジョニングするための十分な時間を確保します。  <br/> |
|2   <br/> |2015/7/22 2:00:00 AM - 7/22/2015 5:59:59 AM  <br/> Set-CsCertificate -Type \<certificate usage type\> -Thumbprint -Roll -EffectiveDate を使用して、有効時間 6:00:00 AM (この例では 4 時間のリード タイムですが、長くすることができます) でエッジ サーバーに証明書を設定する \<thumbprint of new certificate\>\<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |7/22/2015 6:00 AM - 7/22/2015 2:00 PM  <br/> トークンを検証するために、新しい証明書が最初に試され、新しい証明書がトークンの検証に失敗した場合は、古い証明書が試されます。 このプロセスは、8 時間 (既定のトークンの有効期間) の重複期間中のすべてのトークンに使用されます。  <br/> |
|4   <br/> |終了: 2015/7/22 2:00:01 PM  <br/> 古い証明書の有効期限が切れ、新しい証明書が引き継がれています。 古い証明書は、-Type -Previous Remove-CsCertificateして \<certificate usage type\> 安全に削除できます。  <br/> |
   
有効時間 (2015 年 7 月 22 日午前 6:00:00) に達すると、新しいトークンはすべて新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた場合 (2015 年 7 月 22 日午後 2 時 00 分)、トークンは新しい証明書によってのみ検証されます。 以前の証明書は、-Previous パラメーターを指定した Remove-CsCertificate コマンドレットを使用して安全に削除できます。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>-Roll パラメーターと -EffectiveDate パラメーターを使用して OAuthTokenIssuer 証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。
    
2. フロントエンド サーバー上の既存の証明書のエクスポート可能なプライベート キーを使用して、更新または新しい OAuthTokenIssuer 証明書を要求します。
    
3. 新しい OAuthTokenIssuer 証明書をプール内のフロントエンド サーバーにインポートします (プールが展開されている場合)。 OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新および書き換うだけで十分です。 フロントエンド サーバーを例として使用します。
    
4. Set-CsCertificate コマンドレットを使用してインポートした証明書を構成し、-Roll パラメーターを -EffectiveDate パラメーターと一緒に使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。 
    
    -Roll Set-CsCertificate -EffectiveTime パラメーターを指定した次のコマンドを実行します。
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Set-CsCertificate コマンドの例を次に示します。
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate は、サーバーの地域と言語の設定に合わせて書式設定する必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。 
  
有効時間 (2015 年 7 月 21 日午前 1:00:00) に達すると、新しいトークンはすべて新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた場合 (2015 年 7 月 22 日午後 2 時 00 分)、トークンは新しい証明書によってのみ検証されます。 以前の証明書は、-Previous パラメーターを指定した Remove-CsCertificate コマンドレットを使用して安全に削除できます。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>関連項目

[Skype for Business Server でサーバー間認証 (OAuth) とパートナー アプリケーションを管理する](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
