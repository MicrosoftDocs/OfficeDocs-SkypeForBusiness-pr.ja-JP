---
title: 'Lync Server 2013: エンド ユーザーとしての Lync と Skype の接続の使用'
TOCTitle: エンド ユーザーとしての Lync と Skype の接続の使用
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn440175(v=OCS.15)
ms:contentKeyID: 59602763
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用

 

_**トピックの最終更新日:** 2016-12-27_

Lync と Skype の接続によって、Skype ユーザーと Lync ユーザーが互いに連絡先の追加、インスタント メッセージのやり取り、音声通話を実行できるようになりました。Skype ユーザーが Lync ユーザーを追加する場合、Skype ユーザーは Lync ユーザーのセッション開始プロトコル (SIP) の URI (Uniform Resource Identifier) を含む連絡先を Skype に作成します。反対に、Lync ユーザーが Skype の連絡先を追加する場合、Lync ユーザーは、Skype ユーザーの Microsoft アカウント (MSA) (Skype ユーザー名ではない) を含む連絡先を Lync に作成します。

**MSA とは** Skype ユーザーが Lync の連絡先と通信するには、Microsoft アカウント (以前は Windows Live ID と呼ばれていました) で Skype にサインインする必要があります。Microsoft アカウントは、メール アドレスとパスワードの組み合わせで構成され、Microsoft OneDrive ストレージ テクノロジ、Windows Phone、Microsoft Xbox LIVE オンライン ゲーム サービス、Microsoft Outlook メッセージングおよびコラボレーション クライアントなどのサービスへのサインインにも使用できます (以前は Microsoft Hotmail の Web ベースのメール サービスや Windows Live Messenger へのサインインにも使用できました)。メール アドレスとパスワードを使用してこれらのサービスやその他のサービスにサインインしている場合は、既に Microsoft アカウントをお持ちということです。Microsoft アカウントの作成の詳細については、Microsoft アカウントのサインアップ ページ ([http://go.microsoft.com/fwlink/p/?LinkId=306061](http://go.microsoft.com/fwlink/p/?linkid=306061)) を参照してください。既存の Skype アカウントを Microsoft アカウントと結合して、さまざまなアプリケーションやサービスでシングル サインオンできます。アカウントが統合されたら、Skype ユーザーは、連絡先追加のリクエストを Lync ユーザーに送信できます。


> [!IMPORTANT]
> Lync ユーザーと Skype ユーザーが完全に相互通信するには、次の要件を満たす必要があります。 
> <UL>
> <LI>
> <P>Skype ユーザーは Skype クライアントに Microsoft アカウント (MSA) でログインする必要があります。</P>
> <LI>
> <P>Lync ユーザーでは、Lync 管理者によってパブリック IM 接続が有効化されている必要があります。</P>
> <LI>
> <P>Skype ユーザーが Lync の連絡先を追加する場合は、連絡先の名前の下に Lync という単語が表示されることを確認します。これは、Lync URI が見つかっていることを示します。</P>
> <LI>
> <P>Skype ユーザーが Lync の連絡先を追加し、その Lync ドメインで返される検索結果がゼロの場合、PIC プロビジョニング プロセスが完了していないか、その Lync ドメインが設定されていない可能性があります。</P>
> <LI>
> <P>Lync ユーザーや Skype ユーザーのプライバシー設定によっては、新しい連絡先が各ユーザーによって承諾されるまで、IM、ビデオ、プレゼンスが機能しない場合があります。</P></LI></UL>



**Skype の連絡先を Lync 2013 に追加するには**

1.  Lync で \[**連絡先の追加\]、\[外部の連絡先の追加**\] をクリックします。

2.  使用可能な連絡先プロバイダーのリストから、以下のように \[**Skype**\] を選びます。
    
    ![Lync クライアント、Skype 連絡先の追加方法](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Lync クライアント、Skype 連絡先の追加方法")

3.  " **IM アドレス**" フィールドに Skype ユーザーの Microsoft アカウント (MSA) を入力します。

4.  \[**連絡先グループに追加**\] ドロップダウン ボックスで、ユーザーを追加する連絡先グループを選びます。

5.  \[**プライバシー関係の設定**\] ドロップダウン ボックスで適切な連絡先設定を選び、\[**OK**\] をクリックします。

6.  これでユーザーが Lync で連絡先として表示されるようになります。ユーザーを選択し、ユーザー名を右クリックし、\[**連絡先カードの表示**\] をクリックしてユーザーのプロパティを表示します。以下に示すように、\[**通話**\]、\[**Lync 通話**\] の順にクリックして新たに追加された Skype ユーザーとの音声またはビデオ通話を確立することができます。
    
    ![Lync クライアント、連絡先との Lync 通話の開始](images/Dn440175.cd7cb21a-87f7-4bfa-b30c-980d4098d226(OCS.15).jpg "Lync クライアント、連絡先との Lync 通話の開始")

連絡先のサポートの詳細については、「[Lync で連絡先を追加する](http://office.microsoft.com/ja-jp/office365-lync-online-help/add-a-contact-in-lync-ha102828922.aspx)」と「[Lync で外部連絡先を追加する](http://office.microsoft.com/ja-jp/office365-lync-online-help/add-an-external-contact-in-lync-ha104038998.aspx?ctt=5%26origin=ha102828922)」を参照してください。

Skype ユーザーの Microsoft アカウントで <strong>bob@contoso.com</strong> などのカスタム ドメイン名が使用されている場合、Lync ユーザーがその Microsoft アカウントを Lync に追加するには、次の 2 つの方法があります。

1.  \[**連絡先の追加**\] アイコンの使用、または

2.  " **ユーザーまたはルームを検索するか、電話番号を入力します**" フィールドの使用

いずれの場合も、Lync ユーザーは Skype ユーザーのメールを <strong>ユーザー(ドメイン名)@msn.com</strong> の形式で入力する必要があります。


> [!IMPORTANT]
> <STRONG>@live.com、@hotmail.com、@outlook.com</STRONG> というドメイン名を使用する Microsoft アカウントの場合、この手順は不要です。サポートされるカスタム ドメイン名の詳細については、「<A href="http://support.microsoft.com/kb/897567">サポートされているパブリック IM ドメイン</A>」を参照してください。



**カスタム ドメイン名を使用している場合に Skype の連絡先を Lync に追加するには**

1.  Lync で \[**連絡先の追加\]、\[外部の連絡先の追加**\] をクリックします。

2.  使用可能な連絡先プロバイダーのリストから、以下のように \[**Skype**\] を選びます。
    
    ![Lync クライアント、Skype 連絡先の追加方法](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Lync クライアント、Skype 連絡先の追加方法")

3.  " **IM アドレス**" フィールドに、Skype ユーザーの Microsoft アカウント (MSA) を<strong>ユーザー(ドメイン名)@msn.com</strong> の形式で入力します。たとえば bob@contoso.com というユーザーの場合、エントリは以下のように <strong>bob(contoso.com)@msn.com</strong> となります。
    
    ![Lync クライアント、新しい連絡先の設定](images/Dn440175.422e69b5-2c0c-4260-858f-f10309af772f(OCS.15).jpg "Lync クライアント、新しい連絡先の設定")

4.  \[**連絡先グループに追加**\] ドロップダウン リスト ボックスでユーザーを追加する連絡先グループを選びます。

5.  \[**プライバシー関係の設定**\] ドロップダウン リスト ボックスで適切な連絡先設定を選び、\[**OK**\] をクリックします。

6.  Lync ユーザーは、Lync の " **Find someone or a room, or a dial a number (人やルームの検索、または番号のダイヤル)**" フィールドを使用して、次の<strong>ユーザー(ドメイン名)@msn.com</strong> のようなアドレスを追加することもできます。たとえば Microsoft アカウントが bob@contoso.com の場合、エントリは以下のように <strong>bob(contoso.com)@msn.com</strong> となります。
    
    ![Lync クライアントで連絡先を検索する](images/Dn440175.69787db8-f9b9-49e5-b197-b90b10393301(OCS.15).jpg "Lync クライアントで連絡先を検索する")

7.  この手順で前述した手順 4. と 5. に従って連絡先グループに連絡先を追加し、適切なプライバシー関係を選びます。

**Lync の連絡先を Skype に追加するには**

1.  Skype にサインインします。Skype ユーザーは、Microsoft アカウント (MSA) で Skype クライアントにログインする必要があります。
    
    ![Skype クライアント、サインイン ページ](images/Dn440175.b4fd7c5a-be35-4205-80c7-872863b7a91d(OCS.15).jpg "Skype クライアント、サインイン ページ")

2.  \[連絡先の追加\] アイコンを選びます。

3.  Lync で使用する SIP URI (bob@contoso.com など) を選びます。

4.  Skype の検索結果で一致する内容が見つかったら、Lync ユーザー名の下の **Lync** という単語を探します。これは、Skype で Lync クライアントの SIP URI が見つかったことを示します。その名前をクリックします。
    
    ![Skype クライアント、Lync 連絡先の表示](images/Dn440175.4e690a72-1a54-4442-89cf-0fb45ac5f56a(OCS.15).jpg "Skype クライアント、Lync 連絡先の表示")

5.  ウィンドウの右上の \[連絡先の追加\] をクリックします。

6.  新しい連絡先が連絡先リストに追加されますが、リクエストが承諾されるまでは、ステータス アイコンの代わりに疑問符が表示されます。新しい連絡先によってリクエストが承諾されると、その連絡先がオンラインになり、IM 会話や音声/ビデオ通話を行うことができます。
    
    ![Skype クライアント、Lync 連絡先との IM 会話](images/Dn440175.86ca6f81-4db9-45ba-8511-1f7541aaf066(OCS.15).jpg "Skype クライアント、Lync 連絡先との IM 会話")
    

    > [!IMPORTANT]
    > Lync Server の管理者は、着信要求が許可されるように、Lync ユーザーのポリシー設定を構成する必要があります。この設定を行わないと、Lync ユーザーが Skype ユーザーからの連絡先要求を受信できません。Lync ユーザーのポリシー設定の構成によっては、Skype ユーザーの追加要求が Lync クライアントの [<STRONG>新規</STRONG>] タブに表示されます。Lync ユーザーが Skype ユーザーとの通信を開始するには、Skype ユーザーをお気に入りリストか連絡先リストに追加する必要があります。以下の画像は、Lync クライアントの [<STRONG>新規</STRONG>] タブの場所を示しています。

    
    ![Lync クライアント、新しい連絡先ページ](images/Dn440175.b1cf8570-1401-47d9-ab14-b04f0d7e8a7a(OCS.15).jpg "Lync クライアント、新しい連絡先ページ")

Lync ユーザーは、Skype ユーザーから送信される要求が表示されてわかるように、Lync 警告を構成する必要があります。Lync 警告を構成するには、次の手順を完了します。

**Lync 警告を構成するには**

1.  Lync クライアントで \[**オプション**\] アイコンをクリックします。

2.  \[**警告**\] を選びます。

3.  \[**全般的な通知**\] の \[**他のユーザーの連絡先リストに追加された場合に通知する**\] をオンにします。

4.  \[**Lync を使っていない連絡先**\] で \[**招待は許可するが、その他のすべての通信をブロックする**\] を選びます。

5.  \[**OK**\] をクリックして \[オプション\] ウィンドウを閉じます。

![Lync クライアント、\[オプション\] ダイアログ ボックス、\[通知\] ページ](images/Dn440175.b36ed67f-f394-4f66-b60a-b74793001bfc(OCS.15).jpg "Lync クライアント、[オプション] ダイアログ ボックス、[通知] ページ")

