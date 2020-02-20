---
title: 'Lync Server 2013: パブリックユーザーアクセスを制御するポリシーの構成'
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
ms.openlocfilehash: 12a6e5d94cef7c9f25bb1c4091a981603f66da82
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

パブリックインスタントメッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、インターネットサービス、Yahoo\!、AOL の Windows Live ネットワークを含む、パブリック im サービスプロバイダーが提供する im サービスのユーザーと通信することができます。 1つ以上の外部ユーザーアクセスポリシーを構成して、パブリックユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。 パブリック インスタント メッセージング接続は、展開およびユーザーの構成に依存する追加機能です。 この機能は、パブリック IM プロバイダーでのサービスのプロビジョニングにも依存します。 公開プロバイダーを使用するように展開を準備する方法については、「Microsoft Lync Server、Office Communications Server、Live Communications Server のパブリック IM 接続プロビジョニングガイド:」を参照してください。[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>



</div>

Microsoft Lync Server パブリック IM 接続プロビジョニングサイトにアクセスするには、次のリンクを使用します。[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

パブリック ユーザー アクセスを制御するには、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを構成できます。 構成できるポリシーの種類の詳細については、「展開」のドキュメントまたは「計画」のドキュメントの「configure [support for external user access In Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) 」を参照してください。 あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。 Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

IM の招待の場合は、クライアント ソフトウェアによって応答が異なります。 ユーザーが構成したルール (ユーザーのクライアントの [**許可**] および [**禁止**] リストの設定) によって、外部の送信者が明示的に禁止されている場合以外は、要求が受け入れられます。 また、[**許可**] リストに含まれていないユーザーからの IM はすべて禁止することを選択すると、IM の招待をブロックできます。

<div>


> [!NOTE]  
> 組織でフェデレーションを有効にしていなくても、パブリック ユーザー アクセスを制御するポリシーを構成できます。 ただし構成するポリシーは、組織でフェデレーションを有効にした場合にのみ有効となります。 フェデレーションを有効にする方法の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。 また、パブリックユーザーアクセスを制御するユーザーポリシーを指定した場合、このポリシーは、Lync Server が有効になっていて、そのポリシーを使用するように構成されているユーザーにのみ適用されます。 Lync Server にサインインできるパブリックユーザーの指定の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「lync <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">server 2013 で lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</A>」を参照してください。



</div>

以下の手順を使用して、1 つ以上のパブリック IM プロバイダーのユーザーによるアクセスをサポートするポリシーを構成します。

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>パブリック ユーザー アクセスをサポートするように外部アクセス ポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] ページで、次のいずれかの操作を行います。
    
      - パブリック ユーザー アクセスをサポートするようにグローバル ポリシーを構成するには、グローバル ポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。
    
      - 新しいサイト ポリシーを作成するには、[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] で一覧から適切なサイトをクリックし、[**OK**] をクリックします。
    
      - 新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**新しい外部アクセス ポリシー**] の [**名前**] フィールドで、ユーザー ポリシーの適用範囲を示す一意の名前を作成します (たとえば、パブリック ユーザーの通信を有効にするユーザー ポリシーの場合、**EnablePublicUsers** という名前を作成します)。
    
      - 既存のポリシーを変更するには、表に表示されている適切なポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  (オプション) 説明を追加または編集する場合は、[**説明**] でポリシーの情報を指定します。

6.  次のどちらかの操作を行います。
    
      - ポリシーのパブリック ユーザー アクセスを有効にするには、[**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオンにします。
    
      - ポリシーのパブリック ユーザー アクセスを無効にするには、[**パブリック ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

7.  [**確定**] をクリックします。

パブリック ユーザー アクセスを有効にするには、組織でフェデレーションのサポートも有効にする必要があります。 詳細については、「 [Lync Server 2013 でフェデレーションユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。

これがユーザー ポリシーの場合、パブリック ユーザーと共同作業できるようにするパブリック ユーザーに対してもポリシーを適用する必要があります。 詳細については、「 [Lync Server 2013 でユーザーごとのポリシーを割り当てる](lync-server-2013-assigning-per-user-policies.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

