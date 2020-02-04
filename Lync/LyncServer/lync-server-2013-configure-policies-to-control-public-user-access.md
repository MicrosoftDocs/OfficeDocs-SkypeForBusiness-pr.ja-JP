---
title: 'Lync Server 2013: パブリック ユーザー アクセスを制御するポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

パブリックインスタントメッセージング (IM) 接続を使うと、組織内のユーザーは、インターネットサービス、Yahoo\!、AOL の Windows Live ネットワークなど、パブリック im サービスプロバイダーによって提供される im サービスのユーザーと通信することができます。 1つ以上の外部ユーザーアクセスポリシーを構成して、パブリックユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。 パブリックインスタントメッセージング接続は、展開とユーザーの構成に依存する追加機能です。 また、パブリック IM プロバイダーでのサービスのプロビジョニングにも依存します。 パブリックプロバイダーを使用するために展開をプロビジョニングする方法については、「Microsoft Lync Server、Office Communications Server、Live Communications Server 用のパブリック IM 接続プロビジョニングガイド」を参照してください。[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>



</div>

Microsoft Lync Server パブリック IM 接続プロビジョニングサイトにアクセスするには、次のリンクを使用します。[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

パブリックユーザーアクセスを制御するために、グローバル、サイト、ユーザーレベルでポリシーを構成することができます。 構成できるポリシーの種類の詳細については、「展開ドキュメントまたは計画ドキュメントの「 [Lync Server 2013 で外部ユーザーアクセスのサポートを構成](lync-server-2013-configuring-support-for-external-user-access.md)する」を参照してください。 1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

IM 招待の場合、応答はクライアントソフトウェアによって異なります。 外部の送信者が、ユーザーによって構成されたルールによって明示的にブロックされていない限り、要求は承認されます (つまり、ユーザーのクライアントの**許可**リストと**ブロック**リスト内の設定)。 さらに、ユーザーが**許可**リストにないユーザーからのすべての im をブロックすることにした場合、im 招待をブロックすることができます。

<div>


> [!NOTE]  
> 組織のフェデレーションを有効にしていない場合でも、パブリックユーザーアクセスを制御するためのポリシーを構成できます。 ただし、構成したポリシーは、組織でフェデレーションが有効になっている場合にのみ有効になります。 フェデレーションを有効にする方法について詳しくは、展開ドキュメントまたは運用ドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効</A>にする」をご覧ください。 さらに、ユーザーポリシーを指定してパブリックユーザーアクセスを制御している場合、ポリシーは、Lync Server が有効になっていて、ポリシーを使用するように構成されているユーザーにのみ適用されます。 Lync Server にサインインできるパブリックユーザーの指定の詳細については、展開ドキュメントまたは操作のドキュメントの「lync <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">server 2013 での lync 対応ユーザーへの外部ユーザーアクセスポリシーの割り当て</A>」を参照してください。



</div>

次の手順を使用して、1つ以上のパブリック IM プロバイダーのユーザーによるアクセスをサポートするポリシーを構成します。

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>パブリックユーザーのアクセスをサポートするように外部アクセスポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

4.  [**外部アクセスポリシー** ] ページで、次のいずれかの操作を行います。
    
      - パブリックユーザーアクセスをサポートするようにグローバルポリシーを構成するには、グローバルポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
      - 新しいサイトポリシーを作成するには、[**新規**作成] をクリックし、[**サイトポリシー**] をクリックします。 [**サイトの選択**] で、一覧から該当するサイトをクリックし、[ **OK]** をクリックします。
    
      - 新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。 [**新しい外部アクセスポリシー**] で、[**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、パブリックユーザーの通信を可能にするユーザーポリシーの**enablepublicusers** )。
    
      - 既存のポリシーを変更するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  省略説明を追加または編集する場合は、ポリシーの情報を [**説明**] で指定します。

6.  次のいずれかを実行します。
    
      - ポリシーのパブリックユーザーアクセスを有効にするには、[**パブリックユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - ポリシーのパブリックユーザーアクセスを無効にするには、[**パブリックユーザーとの通信を有効に**する] チェックボックスをオフにします。

7.  [**コミット**] をクリックします。

パブリックユーザーアクセスを有効にするには、組織のフェデレーションのサポートも有効にする必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。

ユーザーポリシーの場合は、パブリックユーザーとの共同作業を可能にするパブリックユーザーにもポリシーを適用する必要があります。 詳細については、「 [Lync Server 2013 でユーザーごとのポリシーを割り当てる](lync-server-2013-assigning-per-user-policies.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

