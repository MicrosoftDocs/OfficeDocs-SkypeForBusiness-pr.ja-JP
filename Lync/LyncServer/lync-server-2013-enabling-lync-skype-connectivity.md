---
title: 'Lync Server 2013: Lync と Skype の接続の有効化'
TOCTitle: Lync と Skype の接続の有効化
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn440170(v=OCS.15)
ms:contentKeyID: 59602755
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync と Skype の接続の有効化

 

_**トピックの最終更新日:** 2016-12-08_

プロビジョニング要求を送信した後は、Lync と Skype の接続の構成に必要な、Lync Server の環境と管理タスクに重点を移すことができます。このセクションでは、Lync Server 管理者は Lync Server を展開し、外部アクセスを構成していることが前提になっています。Lync Server の外部アクセスの構成の詳細については、「[Lync Server 2013 の外部ユーザー アクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

Lync と Skype の接続向けに Lync Server 環境を準備するには、Lync Server 管理者は次の 3 つのタスクを完了する必要があります。

## 1\. フェデレーションと PIC を構成する

フェデレーションは、Skype ユーザーが組織内の Lync ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Lync ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、次に示すように Lync Server コントロール パネルを使用して構成します。

![PIC の表示](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC の表示")


> [!IMPORTANT]
> PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。PIC フェデレーションがサポートされるプラットフォームとしては、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。



## 2\. フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する

管理者は Lync Server コントロール パネルを使用して外部ユーザー アクセス ポリシーを 1 つ以上構成し、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。

![ポリシー](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "ポリシー")

## 3\. Lync 用の Skype PIC プロバイダー設定を構成する

管理者は Lync Server 管理シェルを使用して Lync クライアント ポリシーを構成し、Skype を追加の PIC プロバイダーとして表示する必要があります。

> [!NOTE]
> また、管理者が少なくとも 1 つのポリシー (この手続きの手順 2.) を構成してパブリック IM 接続をサポートするまでは、パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは組織の IM、電話およびビデオ会議に参加できません。


1.  フェデレーションと PIC を構成するには、「フェデレーションおよびパブリック IM 接続の有効化または無効化」( [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)) を参照してください。

2.  少なくとも 1 つのポリシーを構成してフェデレーション ユーザーのアクセスをサポートするには、「パブリック ユーザー アクセスを制御するポリシーの構成」( [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)) を参照してください。

**Messenger PIC プロバイダーを編集して Skype 向けに構成するには**

1.  Lync Server フロント エンド サーバーから、Lync Server 管理シェルを開きます。

2.  次の 2 つのコマンドを実行します。
    
    `Remove-CsPublicProvider -Identity Messenger`
    
    `New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png" -VerificationLevel 2 -Enabled 1`

3.  この時点で、Lync クライアントから Skype を PIC プロバイダーとして選び、また Microsoft アカウントを指定して Skype クライアントを追加することができます。加えて、マージされ Microsoft アカウントでログインした Skype ユーザーは、連絡先追加のリクエストを Lync ユーザーに送ることができます。Microsoft アカウントの詳細については、「[Microsoft アカウントとは何ですか?](https://support.skype.com/ja/faq/fa12059/what-is-a-microsoft-account)」を参照してください。Lync へのクライアントの追加の詳細については、「[エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。
    
    ![Skype 連絡先の追加](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype 連絡先の追加")

4.  ホストされるプロバイダーの変更の詳細については、「ホスト SIP フェデレーション プロバイダーの作成または編集」( [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)) を参照してください。

これで、サーバー上で実行する必要がある管理タスクが完了し、Lync と Skype の接続を使用するように設定されました。

