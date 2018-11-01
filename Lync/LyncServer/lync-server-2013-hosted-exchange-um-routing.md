---
title: 'Lync Server 2013: Hosted Exchange UM のルーティング'
TOCTitle: Hosted Exchange UM のルーティング
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48272440
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 Hosted Exchange UM のルーティング

 

_**トピックの最終更新日:** 2012-10-01_

Exchange UM ルーティング アプリケーションは フロント エンド サーバー上で動作し、内部設置型 Microsoft Exchange Server ユニファイド メッセージング (UM) 展開またはホストされた Exchange UM サービスに通話をルーティングします。

## ExUM ルーティング アプリケーション

Lync Server 2013Exchange UM ルーティング アプリケーションは、次の図に示すように、ユーザー アカウント設定の情報と、ホスト ボイス メール ポリシーのパラメーターによる情報を使用して、ホストされたボイス メッセージングの通話をルーティングする方法を決定します。

**Exchange UM ルーティングが混在している展開の例**

![社内の Lync Server Exchange UM 展開](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "社内の Lync Server Exchange UM 展開")

Exchange UM ルーティングは、内部設置型 Exchange UM が有効になっているユーザー、ホストされた Exchange UM が有効になっているユーザー、またはこの 2 つの組み合わせに対して通話をルーティングするように構成できます。

たとえば、Roy のメールボックスと Exchange UM サービスが内部設置型 Exchange 展開に所属しているとします。

  - Roy のユーザー アカウントのプロキシ アドレス情報は、ExUM ルーティング アプリケーションが Roy の通話を内部設置型 Exchange UM サーバーにルーティングする際に使用する情報を提供します。

Alice のメールボックスと Exchange UM サービスは、ホストされた Exchange サービス プロバイダーのデータ センターにあります。Alice の Exchange UM 通話のルーティングは、次のように構成されています。

  - Alice のユーザー アカウントの msExchUCVoiceMailSettings 属性に設定された値は、ExUM ルーティング アプリケーションに対して、ホスト ボイス メール ポリシーのルーティング情報を確認するように示しています。
    
    > [!NOTE]
    > msExchUCVoiceMailSettings 属性の値は、Exchange サービス プロバイダーまたは Lync Server 2013 管理者が設定できます。 上の図の例では、Alice のホスト ボイス メールを有効にするために値 (CsHostedVoiceMail=1) が Lync Server 2013 管理者によって設定されています。この属性の詳細については、「<a href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 の Hosted Exchange ユーザー管理</a>」を参照してください。


  - Alice のユーザー アカウントに割り当てられたホスト ボイス メール ポリシーは、次のルーティング情報を提供します。
    
      - 宛先は、ホストされた Exchange UM サービス プロバイダー (この例では ls.ExUm. *\<hostedExchangeServer\>* .com) です。
    
      - 組織はテナント ID で識別されます。このテナント ID は、ls.ExUm. *\<hostedExchangeServer\>* .com (この例では、corp.contoso.com および corp.litwareinc.com) にある Exchange Server テナントの SIP メッセージのルーティング FQDN です。
        
        > [!NOTE]  
        > Exchange Online の FQDN は exap.um.outlook.com です。
        
        詳細については、「[Lync Server 2013 のホスト型ボイス メール ポリシー](lync-server-2013-hosted-voice-mail-policies.md)」を参照してください。

> [!NOTE]
> msExchUCVoiceMailSettings 属性と UM プロキシ アドレス設定の両方がユーザー アカウントに設定されている場合、msExchUCVoiceMailSettings 属性が優先されます。

