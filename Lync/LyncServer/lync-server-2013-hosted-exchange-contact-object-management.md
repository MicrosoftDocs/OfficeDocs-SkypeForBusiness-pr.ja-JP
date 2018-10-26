---
title: 'Lync Server 2013: Hosted Exchange 連絡先オブジェクト管理'
TOCTitle: Hosted Exchange 連絡先オブジェクト管理
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48273945
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Hosted Exchange 連絡先オブジェクト管理

 

_**トピックの最終更新日:** 2012-09-25_

横断設置型の展開では、自動応答番号およびサブスクライバー アクセス番号ごとに連絡先オブジェクトを構成する必要があります。

Hosted Exchange UM との統合では、ocsumutil.exe は Active Directory Exchange UM 設定に依存するため、ocsumutil.exe を使用して連絡先オブジェクトを管理することはできません。横断設置型の展開では、 Lync Server 2013 と Hosted Exchange UM が両者の間に信頼関係がない別々のフォレストにインストールされます。 Lync Server 2013 の管理者は、セキュリティ上の理由から、Exchange UM の Active Directory 設定に直接アクセスする権限は持ちません。このため、 Lync Server 2013 では、別のモデルが用意され、連絡先オブジェクトは、 Lync Server 2013 と Hosted Exchange UM サービスの両方がアクセスできる共有 SIP アドレス スペース で管理されます。

## ホスト型連絡先オブジェクトのワークフロー

以下では、Hosted Exchange のテナント管理者と協力して、連絡先オブジェクトを管理するための一般的な手順を示します。

1.  Exchange の管理者が、Exchange UM サブスクライバー アクセス連絡先オブジェクトおよび自動応答連絡先オブジェクトの電話番号を要求します。

2.  Lync Server 2013 の管理者が、各電話番号の連絡先オブジェクトを作成して、ホスト ボイス メール ポリシーを各連絡先オブジェクトに割り当てます。

3.  Lync Server 2013 の管理者が、電話番号を Exchange 管理者に提供します。

4.  Exchange 管理者は、自動応答およびサブスクライバー アクセス用の該当する Exchange UM ダイヤルプランに電話番号を割り当てます。

> [!NOTE]
> 内部設置型展開では必要ですが、連絡先オブジェクトに対して、 Lync Server 2013 のダイヤル プラン設定を構成する必要はありません。


## ホスト型連絡先オブジェクトの構成

> [!NOTE]
> Lync Server 2013 の連絡先オブジェクトを Hosted Exchange UM に対して有効化する前に、連絡先オブジェクトに適用されるホスト ボイス メール ポリシーを展開する必要があります。ここで展開するポリシーは、有効化する連絡先オブジェクトに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。詳細については、「<a href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイス メール ポリシー</a>」を参照してください。


横断型展開でホスト型自動応答およびサブスクライバー アクセス連絡先オブジェクトを構成するには、次の各コマンドレットを使用する必要があります。

  - **New-CsExUmContact** は、ホスト型 UM 用の新しい連絡先オブジェクトを作成します。

  - **Set-CsExUmContact** は、Hosted Exchange UM 用の既存の連絡先オブジェクトを変更します。

次の例では、自動応答連絡先オブジェクトが作成されます。

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

この例では、SIP アドレスが sip:exumaa1@fabrikam.com の、新しい Exchange UM 連絡先オブジェクトが作成されます。 Lync Server 2013 のレジストラー サービスが実行されているプールの名前は、RedmondPool.litwareinc.com です。この情報が保存される Active Directory 組織単位は、OU=ExUmContacts,DC=litwareinc,DC=com です。連絡先オブジェクトの電話番号は、2065554567 です。オプションの -AutoAttendant $True パラメーターは、このオブジェクトが自動応答連絡先オブジェクトであることを指定しています。-AutoAttendant パラメーターを False (既定) に設定すると、このオブジェクトがサブスクライバー アクセス連絡先オブジェクトであることが指定されます。

New-CsExUmContact および Set-CsExUmContact コマンドレットの詳細については、 Lync Server 管理シェルのドキュメントを参照してください。

