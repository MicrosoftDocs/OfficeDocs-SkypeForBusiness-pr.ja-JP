---
title: Teams と Skype for Business のクラウド統合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: この記事では、UC ワークロードを Teams に移行する必要がある Skype for Business (または Lync) のオンプレミス展開を持つ組織に対して、その統合を実現する方法について説明します。
ms.openlocfilehash: 99218c2a629a32d61e9625f8a7808d9f95e9f873
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731766"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams と Skype for Business のクラウド統合

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


多くの大規模企業にはオンプレミスの AD フォレストが複数あり、場合によっては、顧客に複数の Exchange または Skype for Business Server (または Lync Server)、あるいはそれらの両方の展開があることがあります。 また、オンプレミスのフォレストが 1 つしかない組織であっても、経営統合や買収によって同様の状況になる可能性があります。 これらの顧客がクラウドに移行すると、特定のオンプレミス ワークロードの複数のインスタンスをクラウドに統合して、1 つの組織に統合Microsoft 365します。 この記事では、組織を完全に Microsoft Teams に移行する複数のオンプレミス展開が Skype for Business (または Lync) の組織で統合される方法について説明します (すべてのユーザーは Teams のみ)。

以前はこのような状況の場合、最初にオンプレミスで展開を統合し、その後クラウドに移行するようご案内してきました。 これはまだオプションですが、この記事では、複数の Skype for Business 展開を持つ組織が、オンプレミスの統合を行わずに、一度に 1 つの展開を 1 つの Microsoft 365 組織に移行できるソリューションについて説明します。 ハイブリッド モードMicrosoft Teams複数のSkype for Business Lync Server フォレストは、1 つの組織でサポートMicrosoft 365注意してください。 

> [!Important]
> 組織に影響する可能性があるため、[制限事項](#limitations)を確認して理解してから、このガイドを構成に使用してください。

## <a name="overview-of-cloud-consolidation"></a>クラウド統合の概要

1 つの Microsoft 365 組織のオンプレミスからクラウドへのすべてのユーザーの統合は、次の重要な要件が満たされている場合に、複数の Skype for Business 展開を持つ任意の組織で実現できます。

- 関連する組織には、少なくとも 1 Microsoft 365必要があります。 複数の組織とのシナリオでの統合はサポートされていません。
- いつでも、ハイブリッド モードにできるオンプレミスの Skype for Business フォレストは 1 つのみです (共有 SIP アドレス スペース)。 他のすべてのオンプレミス Skype for Business フォレストはオンプレミスになければなりません (多くの場合、相互にフェデレーションされます)。 オンライン SIP ドメインを無効にした場合、これらの他のオンプレミス組織は必要にAD Azure サーバーに[同期できます](/powershell/module/skype/disable-csonlinesipdomain)。

複数のフォレストに Skype for Business を展開しているお客様は、単一のハイブリッド Skype for Business フォレストのすべてのユーザーを、共有 SIP アドレス空間機能を使用して Microsoft 365 組織に個別に完全に移行し、次のオンプレミス Skype for Business 展開を移行する前に、そのオンプレミス展開とのハイブリッドを無効にする必要があります。 クラウドへの移行を開始するまでは、オンプレミス ユーザーは、そのユーザーのオンプレミス ディレクトリ内にいないユーザーとフェデレーションした状態のままになります。  

## <a name="canonical-example-of-cloud-consolidation"></a>クラウド統合の標準的な例

2 つのフェデレーションオンプレミス展開が 2 つの組織で、Skype for Businessにオンラインで統合する必要がある組織をMicrosoft Teams。


|元の状態の詳細 |必要な状態の詳細 |
|---------|---------|
|<ul><li>個別の AD フォレストに 2 つの独立した Skype for Business のオンプレミス展開がある<li>多くの場合、1 つのフォレストはハイブリッドとハイブリッドTeams <li> 組織が相互にフェデレーションされている <li>これらのフォレスト間でユーザーが同期されていない<li> 組織には組織が存在Microsoft 365、自分のディレクトリを Azure 組織に同期AD</ul>|<ul> <li>1 Microsoft 365組織<li>オンプレミス展開が不要になるため、ハイブリッドがない<li>オンプレミスのすべてのユーザーが [ユーザーのみ] Teamsに移動されました <li>任意の場所に設置されたSkype for Business Server設置スペースなし <li>ユーザーは引き続きオンプレミス認証が必要である</ul> |

![2 つの個別のフェデレーションオンプレミス展開を統合する。](../media/cloudconsolidationfig1.png)  

元の状態から目的の最終的な状態を実現するための基本的な手順を以下に示します。  組織によっては、開始点が以下の手順の途中にある場合があります。 この記事の後半で説明する「[その他の開始点](#other-starting-points)」を参照してください。 さらに、必要に応じて、順序を調整できる場合もあります。 [重要な制約と制限事項](#limitations)については、後で説明します。

1.  組織がまだMicrosoft 365場合は、組織を取得します。
2.  両方のオンプレミス展開間で関連するすべての SIP ドメインが、すべての関連する SIP ドメインがMicrosoft 365してください。
3.  ハイブリッド展開Skype for Business展開を 1 つ選択Microsoft 365。 この例では、OriginalCompany.<span>com を使用します。
4.  最初にハイブリッドに設定される[フォレストの AAD Connect を有効にします](configure-azure-ad-connect.md) (OriginalCompany.<span>com)。 
5.  [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)のテナント全体のポリシーを SfBWithTeamsCollab または他の SfB モード (SfBOnly または SfBWithTeamsCollabAndMeetings) に設定します。 これは、[Teams のみ] に移行するユーザーからオンプレミスを引き続き使用するユーザーに通話とチャットを確実にルーティングするために不可欠です。
6.  現時点では (ただし、手順 11 までは必須ではありません)、[その他のフォレストの AAD Connect を有効にする](cloud-consolidation-aad-connect.md)ことをお勧めします (AcquiredCompany.<span>com)。 両方のフォレストで AAD Connect が有効になっていると仮定すると、組織は **[図 A](#figure-a)** のようになります。組織によっては、これが一般的な開始点です。 
7.  他のオンプレミス展開によってホストされる SIP ドメイン (この場合は、AcquiredCompany)。 <span>com)[をクリックし](/powershell/module/skype/disable-csonlinesipdomain)、PowerShell モジュールで使用Microsoft 365組織でこれらのオンライン `Disable-CsOnlineSipDomain` SIP ドメインTeams無効にします。 
8.  OriginalCompany.<span>com の [Skype for Business Hybrid を構成します](configure-federation-with-skype-for-business-online.md) (1 つの展開でオンライン SIP ドメインを有効にしたままです)。
9.  ハイブリッド展開 (OriginalCompany. <span>com)[を使用](move-users-between-on-premises-and-cloud.md)して、ユーザーをオンプレミスの Skype for Businessからクラウドに移動し (Teams のみ)、ユーザーが [のみ] Teamsします。 これで、組織は **[図 B](#figure-b)** のようになります。図 A からの主な変更点は次のとおりです。
    - オンプレミスの両方のディレクトリのユーザーが、AAD に存在している。
    - AcquiredCompany.<span>com は、無効なオンライン SIP ドメインである。
    - 一部のユーザーはオンラインで [Teams] に移動されています。 (紫色のユーザー A を参照)。
10. すべてのユーザーがクラウドに移動したら、OriginalCompany のオンプレミスSkype for Business[ハイブリッド](cloud-consolidation-disabling-hybrid.md)を無効にします。 <span>com from Microsoft 365:  
    - 組織で分割ドメインをMicrosoft 365します。
    - OriginalCompany でユーザーと通信Microsoft 365無効にします。 <span>com オンプレミス。
    - OriginalCompany の DNS レコードを更新します。 <span>com をポイントMicrosoft 365。
11. まだ行っていない場合は、ハイブリッドに設定される[次のフォレストの AAD Connect を有効にします](cloud-consolidation-aad-connect.md) (AcquiredCompany.<span>com)。 この時点で、組織は **[図 C](#figure-c)** のようになります。組織によっては、これが別の一般的な開始点になります。 
12. PowerShell Teamsで、ハイブリッドである[](/powershell/module/skype/enable-csonlinesipdomain)AcquiredCompany に移動する次のオンプレミス展開に対して SIP ドメインを有効にしてください。 <span>com. これは、2018 年 12 月時点で利用可能な新機能である `Enable-CsOnlineSipDomain` を使用して行われます。
13. 閉じたフェデレーションを使用している場合は、純粋なオンライン テナントの SIP ドメイン (.microsoftonline.com を除く) を、同じドメイン内の許可ドメインとして追加する \* 必要Microsoft 365。  変更が有効になるまでに時間がかかることがあります。これを早い段階で行っても問題はないため、手順 14 に進む前にこれを行っておくことをお勧めします。
14. オンプレミス環境を更新して、すべての SIP ドメインをオンライン テナントから受け入れ、ドメインが一致するようにします。
    - 以前と同じ値になるように、[すべてのエッジ証明書の SAN を更新して](cloud-consolidation-edge-certificates.md)、さらに既存のオンライン SIP ドメイン (*.microsoftonline.com を除く) を加えます。この場合は、Sip.OriginalCompany.<span>com になります。
    - OriginalCompany.<span>com がオンプレミス展開である AcquiredCompany の[許可ドメイン](/powershell/module/skype/new-csalloweddomain)であることを確認してください。 許可ドメインを追加します。
15. オンプレミスの AcquiredCompany.<span>com とクラウドの間で [Skype for Business Hybrid を有効にします](configure-federation-with-skype-for-business-online.md)。
16. 必要に応じて [、ユーザーをオンプレミスから](move-users-between-on-premises-and-cloud.md) クラウドに移行して [TeamsOnly ユーザーになります](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability)。 この段階では、組織は **[図 D](#figure-d)** のようになります。
17. すべてのユーザーを移行した後、[オンプレミス環境とのハイブリッドを無効にして](cloud-consolidation-disabling-hybrid.md)、*組織を純粋なクラウドにします*。

以下の図面は、このプロセスにおけるさまざまな重要なポイントでの構成を示しています。

##### <a name="figure-a"></a>図 A:

- 両方の組織が AAD Connect を介して同期されるため、AAD には両方のオンプレミス展開のすべてのユーザーが存在しています。
- すべてのユーザーがオンプレミスに所属しています。  
- Skype for Business Hybrid はまだ構成 *されていません*。
- いずれかの展開のユーザーが Teams を使用している場合、ユーザーは他のユーザー (または任意の組織) と相互にフェデレーションすることも、Skype for Business ユーザーとの相互運用性を確保することもできません。 この段階では、Microsoft はチャネルでのみ Teams を使用することをお勧めします。<br><br>
    ![図 図](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>図 B:

- AcquiredCompany.<span>com は、[無効な](/powershell/module/skype/disable-csonlinesipdomain)オンライン SIP ドメインです。 すべてのユーザーがオンプレミスに存在しています。 ユーザーが Teams を使用する場合、フェデレーションまたは相互運用性はありません。 この段階では、Microsoft はチャネルでのみ Teams を使用することをお勧めします。
- Skype for Business Hybrid は、オンプレミス組織のいずれかで有効になっています。
- ハイブリッド組織の一部のユーザーはクラウドに移動され、Teamsのみ (紫色の網かけで示されているユーザー A) になります。 これらのユーザー Teamsユーザーのみ、他のユーザーと完全な相互運用性とフェデレーションSkype for Businessがあります。<br><br>
    ![図 B の図。](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>図 C:

- OriginalCompany のすべてのユーザー。 <span>com はクラウドTeamsのみモードになります。 
- OriginalCompany.<span>com が展開された Skype for Business Hybrid の構成は無効になっています。 オンプレミス展開がなくなりました。
- AcquiredCompany.<span>com が以前に AAD に同期されていなかった場合、ここから続行するには今すぐ同期させる必要があります。 ただし、まだハイブリッド (共有 SIP アドレス スペース) に設定されていません。組織がハイブリッドに移行する準備ができるまで、純粋なオンプレミス組織のオンライン SIP ドメイン (AcquiredCompany.com) を無効のままにして、オンラインの Team ユーザーがオンプレミスのユーザーと通信できるようする必要があります。<br><br>
    ![図 C の図。](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>図 D:

- AcquiredCompany.<span>com がオンライン SIP ドメインとして有効になりました。
- オンプレミスは、OriginalCompany.<span>com を受け入れるように更新されます (許可ドメインとエッジ証明書の両方が更新されます)。
- 共有 SIP アドレス空間は、AcquiredCompany 間で有効になります。 <span>com および Microsoft 365組織。
- 以下のユーザー D (紫色の網掛けで示されているユーザー) など、ハイブリッド組織の一部のユーザーがクラウドに移行されている可能性があります。<br><br>
    ![図 D の図。](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>その他の開始点

上記の標準的な例の手順では、組織が 2 つのフェデレーションオンプレミス展開から始まり、プレゼンスがMicrosoft 365前提とします。 ただし、一部の組織では、既存のMicrosoft 365を持つ場合があります。また、上記のシーケンスへのエントリ ポイントが異なる場合があります。 一般的な構成は以下の 4 つです。

- 複数のフェデレーションオンプレミス組織で、組織にMicrosoft 365はありません。 この場合は、手順 1 から開始します。
- 複数の Skype for Business のフォレストが単一の Azure AD テナントに既に同期されている複数のフェデレーション オンプレミス組織。 このような組織は、図 A に示す仮定の組織のようになります。手順 1 から 6 は完了しているため、手順 7 から開始する必要があります。
- 1 つまたは複数の他の純粋なオンプレミス組織とフェデレーションするハイブリッド組織。いずれも AAD と同期しません。 このような組織は、以下に示す **図 E** の仮定の組織のようになります。
    - この組織は図 B のようになり、手順 1 から 9 は完了しています。ただし、次の点を除きます。
        - 組織の非ハイブリッドの Skype for Business 展開は、まだ Azure AD と同期 *していない*。
        -  オンライン SIP ドメインがまだ無効になっていない。 
    - これらの組織は、次のいずれかの操作を行う必要があります。
        - 既存のハイブリッド組織の移行を完了し、上記の手順 10 から開始します。  または、
        - ハイブリッド組織の移行を完了する前にその他の Skype for Business フォレストを AAD に同期する必要がある場合は、組織は手順 7 (AAD と同期するその他のオンプレミス Skype for Business 展開のすべてのオンライン SIP ドメインを無効にする) を実行する必要があります。その後、AAD Connect を有効にして、手順 10 (元のハイブリッド展開の使用を停止する) に進みます。  
                **図 E**<br>
                ![図 E の図。](../media/cloudconsolidationfige.png)
- 純粋なTeams、個別のオンプレミスの組織とフェデレーションするSkype for Businessです。 この組織がオンプレミス組織のオンライン SIP ドメインを無効にして、オンプレミスの Skype for Business 組織の AAD Connect を有効にした場合、この組織は **[図 C](#figure-c)** に示す仮定の組織のようになり、既に手順 1 から 11 は完了しています。

## <a name="limitations"></a>制限事項

- 関連する組織には、少なくとも 1 Microsoft 365必要があります。 複数の組織とのシナリオでの統合はサポートされていません。
- 一度にハイブリッド モード (共有 SIP アドレス スペース) にできるオンプレミスの Skype for Business フォレストは 1 つのみです。 他のすべてのオンプレミス のSkype for Businessフォレストは、完全にオンプレミスのままで、互いにフェデレーションし、組織Microsoft 365があります。
- クラウドに移行する前は、この展開に存在するユーザーのエクスペリエンスは非対称です。これは、オンラインのすべてのユーザーがオンプレミスで表されるわけではないためです。
    - エクスペリエンスを要約すると次のようになります。
        - オンラインに所属しているユーザーは、自分がハイブリッド ユーザーであるかのようにハイブリッド環境のオンプレミス ユーザーと対話する。
        - ハイブリッド展開のオンプレミス ユーザーは、オンプレミス ディレクトリに表されているオンライン ユーザーをハイブリッド ユーザーであるかのように扱って対話する。 
        - ハイブリッド展開のオンプレミス ユーザーは、オンプレミス AD に表されていないオンライン ユーザーをフェデレーション ユーザーであるかのように扱って対話する。
    - 上記の **[図 D](#figure-d)** では、ユーザー E は AcquiredCompany.<span>com のオンプレミス ユーザーです。  ユーザー E は、標準のハイブリッド エクスペリエンスを使用して、ユーザー D (オンラインに所属) と対話しますが、ユーザー E はユーザー A、B、C とフェデレーションされます。これは、ユーザー A、B、C がオンプレミス ディレクトリに表されないためです。 ただし、ユーザー A、B、C は、ユーザー E をハイブリッド ユーザーであるかのように扱って対話します。
    - ハイブリッドとフェデレーション間の相互作用による影響
        - フェデレーション ユーザーのプレゼンスは、ユーザーが連絡先としてマークされている場合を除き、自動的に登録されることはありません。
        - 着信転送はフェデレーション ドメイン間では機能しません。
        - 通話転送のシナリオには多くの制限があります。
        - フェデレーション トラフィックに調整を適用できます。
- この非対称なエクスペリエンスでは、オンプレミス ユーザーとオンプレミス ディレクトリに含まれていないクラウド ユーザー間では、クロスプレミス シナリオの通話機能に対する公式なサポートはピア ツー ピアのみに制限されています。 
    - これらのユーザー間における着信転送、通話転送、通話キューなどは、サポートされていません。
    - これらのサポートされていない通話のシナリオは引き続き有効のように見えますが、多くの場合、予期しない動作が発生して失敗します。 
    - 上記の **[図 D](#figure-d)** では、ユーザー E はオンプレミス ユーザーであり、ユーザー A、B、C との通話はピア ツー ピアとしてのみサポートされます (ユーザー D との通話のサポートには制限はありません)。ただし、オンプレミス ユーザー E をクラウドに移行すると、この制限は適用されなくなります。
- お使いの環境で Skype for Business Server 2019 の展開が複数ある場合、組織自動アテンダントを使用するように構成できる展開はそのうちの 1 つだけです。これは、その機能には Skype for Business Server Hybrid 構成が必要なためです。 
- 前の手順の順序は一部調整できます。 そのためには、次のすべての条件に当てはまる必要があります。
    - Azure Skype for Business内の 1 つの Microsoft 365テナントに同期する複数のオンプレミス AD。
    - 分割ドメインが 1 つのオンプレミス フォレストで有効になっている
    - ハイブリッド組織内の少なくとも 1 人のユーザーがクラウドに移行されている<br>   その後、その他のオンライン SIP ドメインを他のオンプレミスの Skype for Business フォレストですべて無効にする *必要があります*。 無効にしないと、ハイブリッド組織のオンライン ユーザーとそれ以外の組織のオンプレミス ユーザー間のフェデレーションが一方向で中断されます。

## <a name="implications"></a>影響

- 上記で説明したように、高度な通話機能のサポートには制限があるため、**組織はこのような非対称な状態を移行の一環として一時的なものとして扱い、安定状態として追求する必要はありません**。  
- 一般的に、オンプレミスの Skype for Business の展開が複数ある組織は、クラウドに完全に移行できる展開を使用して開始し、統合を継続することができます。 場合によっては、Teams にまだ移行することができない特定のユーザー グループのホールドアウトが発生します。 複数の Skype for Business フォレストが関係するシナリオでこれを考慮する場合は、可能な限り、これらの制限がない別のフォレストを使用して移行を開始します。
- オンプレミスからクラウドに移行する場合、委任関係のあるユーザーや通常は着信転送シナリオに関係するユーザーは、1 つの単位として一緒に移行させる必要があります。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>[Teams のみ] モードに移行する場合の考慮事項

ハイブリッド環境でオンプレミスからクラウドにユーザーを移動すると、これらのユーザーは Teamsのみになります。

- [Teams のみ] モードをユーザーに割り当てると、他のユーザーからのチャットと通話はすべて、そのユーザーの Teams クライアントに届きます。 
- オンプレミスの Skype for Business を使用しているユーザーが Teams ではなく、主に Skype for Business クライアントを使用している場合は、これらのオンプレミス ユーザーへのルーティングが Teams ではなく Skype for Business に常に届くように TeamsUpgradePolicy を設定することを検討してください。 [Teams のみ] のユーザーと引き続きオンプレミスの Skype for Business を使用しているユーザー間でチャットと通話を適切にルーティングするには、オンプレミス ユーザーに [アイランド] モード (既定値) ではなく、いずれかの SfB モードで有効な TeamsUpgradePolicy の値が設定されている必要があります。 
    - これを行うには、*まず TeamsUpgradePolicy のテナントのグローバル インスタンスを次の値のいずれかに設定する必要があります*。
        - SfBWithTeamsCollab (推奨)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 次のコマンドを使用して、テナント全体のポリシーを付与できます。<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 注: オンライン ディレクトリの SIP アドレスがない個々のユーザーにはポリシーを割り当てることはできないため、テナント全体レベルでこの手順を実行する必要があります。 純粋なオンプレミス展開ではオンライン SIP ドメインを無効にしていますが、それらのドメインのユーザーには、オンライン ディレクトリの SIP アドレスがありません。これは意図した仕様です。 そのため、オンプレミス ユーザーにポリシーを適用するには、テナント レベルで割り当てる方法しかありません。 一方、ハイブリッド展開では、ユーザーはオンライン ディレクトリの SIP アドレスがあるため、ユーザーがテナントのグローバル ポリシーとは異なる値を必要とする場合、明示的にポリシーを割り当てることができます。

## <a name="see-also"></a>関連項目

[エッジ証明書の更新](cloud-consolidation-edge-certificates.md)

[AAD Connect を更新して複数のフォレストを含める](cloud-consolidation-aad-connect.md)

[ハイブリッドを無効にしてクラウドへの移行を完了する](cloud-consolidation-disabling-hybrid.md)
