---
title: Skype for Business Server でのステージ AV と OAuth 証明書の使用-ロールでのセットアップ-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: '概要: Skype for Business Server 用の AV と OAuth 証明書のステージ'
ms.openlocfilehash: 37edb6843d420ca3387958c54b3db8c72a28be92
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991962"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Skype for Business Server でのステージ AV と OAuth 証明書の使用-ロールでのセットアップ-CsCertificate
 
**概要:** Skype for Business Server 用の AV と OAuth 証明書のステージ
  
音声/ビデオ (A/V) 通信は、Skype for Business Server の主要コンポーネントです。 アプリケーション共有、音声会議、ビデオ会議などの機能は、A/v Edge サービスに割り当てられている証明書、特に A/V 認証サービスに依存しています。
  
> [!IMPORTANT]
> この新機能は、A/V Edge サービスと OAuthTokenIssuer 証明書で動作するように設計されています。 その他の種類の証明書は、A/V Edge サービスと OAuth 証明書の種類と共にプロビジョニングできますが、A/V Edge サービス証明書の共存動作の恩恵を受けることはできません。
  
Skype for business server 管理シェル PowerShell コマンドレットは、Skype for Business Server 証明書を管理するために使用されます。 AudioVideoAuthentication certificate 型としての A/V Edge サービス証明書と、typeOAuthTokenIssuer としての OAuthServer certificate を参照してください。 このトピックの残りの部分では、証明書を一意に識別するために、同じ識別子の型 (AudioVideoAuthentication andOAuthTokenIssuer) によって参照されます。
  
A/V 認証サービスは、クライアントや他の A/V コンシューマーによって使用されるトークンの発行を担当します。 トークンは証明書の属性から生成され、証明書の有効期限が切れたときに、新しい証明書によって生成された新しいトークンに接続を切断して、もう一度参加するための要件があります。 Skype for Business Server の新機能により、この問題が軽減されます。新しい証明書を古いものから事前にステージングし、両方の証明書を一定期間有効にし続けることができます。 この機能では、Set-CsCertificate Skype for Business Server Management Shell コマンドレットの更新された機能を使用します。 既存のパラメーター-EffectiveDate を使用した新しいパラメーター-Roll は、新しい AudioVideoAuthentication 証明書を証明書ストアに配置します。 以前の AudioVideoAuthentication 証明書は、確認のために発行されたトークンのまま残ります。 新しい AudioVideoAuthentication 証明書を所定の場所に配置すると、次の一連のイベントが発生します。
  
> [!TIP]
> Skype for Business Server 管理シェルコマンドレットを使用して、証明書を管理するために、エッジサーバー上の各目的に個別の証明書を要求できます。 Skype for Business Server 展開ウィザードで証明書ウィザードを使用すると、証明書を作成できますが、通常は、Edge Server で使用されるすべての証明書を1つの証明書に結合する**既定**の種類があります。 ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。 既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。 ユーザー (たとえば、証明書の有効期限が切れたときのインスタントメッセージの会話) では、アクセスエッジサービスに関連付けられた新しい証明書を使用するためにログアウトしてもう一度ログインする必要があります。 Web 会議エッジサービスを使って Web 会議に参加しているユーザーに対しても同様の動作が発生します。 OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。 証明書を1か所で作成して管理すると、その証明書は、他のすべてのサーバーの中央管理ストアに保存されます。
  
Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。 -ロールパラメーターは重要ですが、基本的に単一目的です。 パラメーターとして定義すると、証明書が作成されるときに、(AudioVideoAuthentication と OAuthTokenIssuer など) によって定義された証明書に関する情報を提供するように設定されます。有効になっている-EffectiveDate
  
 **-ロール**:-ロールパラメーターは必須で、そのパラメーターと共に指定する必要がある依存関係が含まれています。 どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。
  
 **-EffectiveDate**: パラメーター-EffectiveDate は、新しい証明書が現在の証明書と相互に共存するタイミングを定義します。 -EffectiveDate は、現在の証明書の有効期限が近づいているか、または長い時間が経過している可能性があります。 AudioVideoAuthentication certificate の推奨される最小値は8時間で、AudioVideoAuthentication certificate を使って発行される AV Edge サービストークンの既定のトークンの有効期間です。
  
OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。
  
 **-Thumbprint**: 拇印は証明書の属性で、証明書ごとに一意となります。 -Thumbprint パラメーターは、Set-CsCertificate コマンドレットの操作によって影響を受ける証明書を識別するために使用されます。
  
 **-** Type:-型パラメーターは、1つの証明書の使用の種類、または証明書の使用の種類のコンマ区切りリストを受け入れることができます。 証明書の種類は、コマンドレットに対して識別するものであり、証明書の目的はサーバーに対して指定されています。 たとえば、「AudioVideoAuthentication」と入力すると、A/V Edge サービスと AV 認証サービスが使用されます。 異なる種類の証明書を同時にステージングおよびプロビジョニングすることにした場合は、証明書に必要な最も長い最小のリードタイムを考慮する必要があります。 たとえば、AudioVideoAuthentication と OAuthTokenIssuer の証明書をステージする必要があります。 少なくとも EffectiveDate は、この2つの証明書の大部分である必要があります。この例では、最小のリード時間が24時間となっています。 オーディオビデオ認証証明書のステージが24時間の間にない場合は、要件により多くの EffectiveDate と個別にステージを整理します。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>ロールと-EffectiveDate のパラメーターを使用して A/V エッジサービス証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。
    
2. A/V Edge サービス上の既存の証明書のエクスポート可能な秘密キーを使って、更新または新しい AudioVideoAuthentication 証明書を要求します。
    
3. 新しい AudioVideoAuthentication 証明書を、エッジサーバーとプール内の他のすべてのエッジサーバーにインポートします (プールが展開されている場合)。
    
4. EffectiveDate パラメーターを指定して、インポートされた証明書を構成し、--------------------------- 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。 これにより、証明書がアクティブに設定されている必要があります。 \<また\>、-EffectiveDate 文字列は "7/22/2015 6:00:00 AM" となります。 
    
    > [!IMPORTANT]
    > エッジプールの場合、すべてのクライアントとコンシューマーのトークンが新しい証明書を使用して更新される前に、古い証明書の EffectiveDate パラメーターで定義された日付と時刻を使って、すべての AudioVideoAuthentication 証明書を展開し、プロビジョニングする必要があります。 
  
    EffectiveTime パラメーターを指定した Set CsCertificate コマンドは、次のようになります。
    
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
    > EffectiveDate は、サーバーの地域と言語の設定に合わせて書式設定されている必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。 
  
使用中の AudioVideoAuthentication を検証するために既存の証明書を使用しているときに、新しい AudioVideoAuthentication トークンを発行するための新しい証明書をステージングするために、EffectiveDate を使用して新しいオーディオを発行するための新しい証明書のステージングに使用されるプロセスをさらに理解するコンシューマーは、視覚的なタイムラインは、プロセスを理解するための効果的な手段です。 次の例では、管理者は、A/V Edge サービス証明書が07/22/2015 の 2:00:00 PM に有効期限切れになっていることを確認します。 彼は、新しい証明書を要求して受け取り、その証明書を自分のプールの各エッジサーバーにインポートします。 07/22/2015 の午前2時には、ロールを使用して 07/22/2015 6:00:00 EffectiveTime の証明書を実行します。-------------------------------------------- 各エッジサーバーでこのコマンドを実行します。
  
![Roll および EffectiveDate パラメーターの使用](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**コールアウト**|**ステージ**|
|:-----|:-----|
|1  <br/> |開始: 2015 年 7 月 22 日午前 12:00:00  <br/> 現在の AudioVideoAuthentication 証明書の有効期限が 2015 年 7 月 22 日の午後 2:00:00 に終了します。これは証明書の有効期限タイムスタンプにより決定されます。既存の証明書が有効期限に達する前の 8 時間のオーバーラップ (既定のトークン寿命) を考慮して、証明書の交換とロールオーバーを計画します。この例では、午前 2:00:00 のリード タイムを使用して、管理者が有効時刻の午前 6:00:00 の前に新しい証明書を配置およびプロビジョニングするための適切な時間を確保しています。  <br/> |
|両面  <br/> |2015 年 7 月 22 日午前 2:00:00 ～ 2015 年 7 月 22 日午前 5:59:59  <br/> 有効な時間が 6:00:00 AM (この例では4時間のリードタイム) を使用してエッジサーバー上の証明書\<を設定しますが、新しい証明書\>の有効\<時間を指定し\>た [新しい証明\<書の種類-ロール-EffectiveDate datetime]\>  <br/> |
|3  <br/> |2015 年 7 月 22 日午前 6:00 ～ 2015 年 7 月 22 日午後 2:00  <br/> トークンを検証するためにまず新しい証明書が試されます。新しい証明書でトークンの検証に失敗した場合、古い証明書が試されます。8 時間 (既定のトークン寿命) のオーバーラップ期間中にすべてのトークンにこの処理が適用されます。  <br/> |
|4  <br/> |終了: 2015 年 7 月 22 日午後 2:00:01  <br/> 古い証明書の期限が切れ、新しい証明書に引き継がれます。 以前の証明書を削除するには、削除\<\>する必要があります。  <br/> |
   
有効時刻 (2015 年 7 月 22 日午前 6:00:00) になると、新しいトークンはすべて新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた後は (2015 年 7 月 22 日午後 2:00)、トークンは新しい証明書のみを使用して検証されます。 古い証明書は、前のパラメーターを指定して、CsCertificate Certificate コマンドレットを使用して、安全に削除できます。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>ロールと-EffectiveDate のパラメーターを使用して OAuthTokenIssuer 証明書を更新または更新するには

1. Administrators グループのメンバーとして、ローカル コンピューターにログオンします。
    
2. フロントエンドサーバー上の既存の証明書のエクスポート可能な秘密キーを使って、更新または新しい OAuthTokenIssuer 証明書を要求します。
    
3. 新しい OAuthTokenIssuer 証明書を、プールのフロントエンドサーバーにインポートします (プールが展開されている場合)。 OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新と書き換えを行うだけで十分です。 フロントエンドサーバーは例として使用されます。
    
4. EffectiveDate パラメーターを指定して、インポートされた証明書を構成し、--------------------------- 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。 
    
    EffectiveTime パラメーターを指定した Set CsCertificate コマンドは、次のようになります。
    
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
> EffectiveDate は、サーバーの地域と言語の設定に合わせて書式設定されている必要があります。 この例で使用している地域と言語の設定は英語 (米国) です。 
  
有効時刻 (2015 年 7 月 21 日午前 1:00) になると、新しいトークンはすべて新しい証明書によって発行されます。 トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。 検証が失敗した場合は、古い証明書が試されます。 新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。 古い証明書の有効期限が切れた後は (2015 年 7 月 22 日午後 2:00)、トークンは新しい証明書のみを使用して検証されます。 古い証明書は、前のパラメーターを指定して、CsCertificate Certificate コマンドレットを使用して、安全に削除できます。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>関連項目

[Skype for Business Server でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](server-to-server-and-partner-applications.md)

[設定-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[CsCertificate の削除](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
