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
localization_priority: Normal
description: この記事では、Skype for Business (または Lync) をオンプレミスに展開している組織が、UC ワークロードを Teams や Skype for Business on the web に移行することを検討している場合、そのような統合をどのように実現するかを説明しています。
ms.openlocfilehash: 7f3ad27404ec80e0592baa7174b01363f1aa0ed1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726957"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams と Skype for Business のクラウド統合

多くの大規模企業にはオンプレミスの AD フォレストが複数あり、場合によっては、顧客に複数の Exchange または Skype for Business Server (または Lync Server)、あるいはそれらの両方の展開があることがあります。 また、オンプレミスのフォレストが 1 つしかない組織であっても、経営統合や買収によって同様の状況になる可能性があります。 こうした顧客がクラウドに移行すると、特定のオンプレミス ワークロードの複数のインスタンスを、クラウドの単一の Office 365 テナントに統合することを希望します。 この記事では、Skype for Business (または Lync) のオンプレミス展開が複数ある組織が、UC ワークロードを Microsoft クラウド (Microsoft Teams や Skype for Business on the web など) に移行することを希望する場合、そのような統合をどのように実現するかを説明しています。

以前はこのような状況の場合、最初にオンプレミスで展開を統合し、その後クラウドに移行するようご案内してきました。 これは今でも選択肢の 1 つですが、この記事では、組織に Skype for Business 展開が複数ある場合に、オンプレミスの統合を行うことなく、一度に 1 つの展開を単一の Office 365 テナントに移行することができる新しい機能を使用するソリューションについて取り上げます。 この新しい機能を使用しても、Skype for Business on the web と Microsoft Teams では、単一の Office 365 テナントでハイブリッド モードを使用する場合、複数の Skype for Business/Lync フォレストはサポートされていません。 

> [!Important]
> 組織に影響する可能性があるため、[制限事項](#limitations)を確認して理解してから、このガイドを構成に使用してください。

## <a name="overview-of-cloud-consolidation"></a>クラウド統合の概要

オンプレミスのすべてのユーザーを単一の Office 365 テナント内のクラウドに統合する操作は、以下の主要な要件を満たしている限り、複数の Skype for Business 展開があるあらゆる組織で行うことができます。

- 関係する Office 365 テナントは 1 つでなければなりません。 複数の Office 365 テナントが関係するシナリオでの統合はサポートされていません。
- いつでも、ハイブリッド モードにできるオンプレミスの Skype for Business フォレストは 1 つのみです (共有 SIP アドレス スペース)。 他のすべてのオンプレミス Skype for Business フォレストはオンプレミスになければなりません (多くの場合、相互にフェデレーションされます)。 これらの他のオンプレミス組織は、必要な場合には 2018 年 12 月以降使用可能になっている[オンライン SIP ドメインを無効にする新しい機能](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps)を使用して、AAD と同期*できます*。

複数のフォレストに Skype for Business 展開が複数ある顧客は、共有 SIP アドレス スペース機能を使用してそれぞれの単一のハイブリッド Skype for Business フォレスト内のすべてのユーザーを Office 365 テナントに完全に移行し、次のオンプレミス Skype for Business 展開の移行を開始する前に、対象オンプレミス展開でのハイブリッドを無効にする必要があります。 クラウドへの移行を開始するまでは、オンプレミス ユーザーは、そのユーザーのオンプレミス ディレクトリ内にいないユーザーとフェデレーションした状態のままになります。  

## <a name="canonical-example-of-cloud-consolidation"></a>クラウド統合の標準的な例

Skype for Business の 2 つの独立したフェデレーション オンプレミス展開を持つ組織が、それらを Microsoft Teams または Skype for Business on the web でオンライン統合することを希望している場合について考えます。


|元の状態の詳細 |必要な状態の詳細 |
|---------|---------|
|<ul><li>個別の AD フォレストに 2 つの独立した Skype for Business のオンプレミス展開がある<li>最大 1 つのフォレストで、Skype for Business on the web とのハイブリッドが設定されている <li> 組織が相互にフェデレーションされている <li>これらのフォレスト間でユーザーが同期されていない<li> 組織に Office 365 テナントがあり、ディレクトリを Azure AD に同期している可能性がある</ul>|<ul> <li>Office 365 テナントは 1 つ<li>オンプレミス展開が不要になるため、ハイブリッドがない<li>オンプレミスのすべてのユーザーが Skype for Business on the web に所属しており、場合によっては [Teams のみ] のユーザーである <li>Skype for Business のオンプレミスのフットプリントがどこにもない <li>ユーザーは引き続きオンプレミス認証が必要である</ul> |

![2 つの独立したフェデレーション オンプレミス展開の統合](../media/cloudconsolidationfig1.png)  

元の状態から目的の最終的な状態を実現するための基本的な手順を以下に示します。  組織によっては、開始点が以下の手順の途中にある場合があります。 この記事の後半で説明する「[その他の開始点](#other-starting-points)」を参照してください。 さらに、必要に応じて、順序を調整できる場合もあります。 [重要な制約と制限事項](#limitations)については、後で説明します。

1.  Office 365 テナントがまだ存在しない場合は、入手します。
2.  両方のオンプレミス展開で関連するすべての SIP ドメインが検証済みの Office 365 ドメインであることを確認します。
3.  Office 365 とのハイブリッドを設定する Skype for Business を 1 つ選択します。 この例では、OriginalCompany.<span>com を使用します。
4.  最初にハイブリッドに設定される[フォレストの AAD Connect を有効にします](configure-azure-ad-connect.md) (OriginalCompany.<span>com)。 
5.  Teams を組織に導入する場合は、[TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) のテナント全体のポリシーを SfBWithTeamsCollab または他のいずれかの SfB モード (SfBOnly または SfBWithTeamsCollabAndMeetings) に設定します。 これは、[Teams のみ] に移行するユーザーからオンプレミスを引き続き使用するユーザーに通話とチャットを確実にルーティングするために不可欠です。
6.  現時点では (ただし、手順 11 までは必須ではありません)、[その他のフォレストの AAD Connect を有効にする](cloud-consolidation-aad-connect.md)ことをお勧めします (AcquiredCompany.<span>com)。 両方のフォレストで AAD Connect が有効になっていると仮定すると、組織は**[図 A](#figure-a)** のようになります。組織によっては、これが一般的な開始点です。 
7.  その他のオンプレミス展開でホストされている SIP ドメイン (この場合は、AcquiredCompany.<span>com) の場合は、PowerShell で `Disable-CsOnlineSipDomain` を使用して、[Skype for Business on the web でこれらの SIP ドメインを無効にします](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) (これは 2018 年 12 月時点の新機能です)。
8.  OriginalCompany.<span>com の [Skype for Business Hybrid を構成します](configure-federation-with-skype-for-business-online.md) (1 つの展開でオンライン SIP ドメインを有効にしたままです)。
9.  ハイブリッド展開 (OriginalCompany.<span>com) で、[オンプレミスの Skype for Business からクラウドへのユーザーの移行](move-users-between-on-premises-and-cloud.md) ([Teams のみ] かどうかに関係なく) を開始し、アカウントが Skype for Business on the web に所属するようにします。 これで、組織は**[図 B](#figure-b)** のようになります。図 A からの主な変更点は次のとおりです。
    - オンプレミスの両方のディレクトリのユーザーが、AAD に存在している。
    - AcquiredCompany.<span>com は、無効なオンライン SIP ドメインである。
    - 一部のユーザーが、Skype for Business on the web または Teams のいずれかにオンラインで移行されている (紫色のユーザー A を参照)。
10. すべてのユーザーをクラウドに移行した後、Office 365 で OriginalCompany.<span>com の [Skype for Business オンプレミス展開とのハイブリッドを無効にします](cloud-consolidation-disabling-hybrid.md)。  
    - Office 365 テナントの分割ドメインを無効にする。
    - オンプレミスの OriginalCompany.<span>com で Office 365 と通信する機能を無効にする。
    - OriginalCompany.<span>com の DNS レコードを更新して、Office 365 を指すようにする。
11. まだ行っていない場合は、ハイブリッドに設定される[次のフォレストの AAD Connect を有効にします](cloud-consolidation-aad-connect.md) (AcquiredCompany.<span>com)。 この時点で、組織は**[図 C](#figure-c)** のようになります。組織によっては、これが別の一般的な開始点になります。 
12. PowerShell で、ハイブリッドに設定される[次のオンプレミス展開の SIP ドメインを有効にします](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) (AcquiredCompany.<span>com)。 これは、2018 年 12 月時点で利用可能な新機能である `Enable-CsOnlineSipDomain` を使用して行われます。
13. クローズド フェデレーションを使用している場合、純粋なオンライン テナントの SIP ドメイン (*.microsoftonline.com を除く) を**同じ** Office 365 の許可ドメインとして追加する必要があります。 変更が有効になるまでに時間がかかることがあります。これを早い段階で行っても問題はないため、手順 14 に進む前にこれを行っておくことをお勧めします。
14. オンプレミス環境を更新して、すべての SIP ドメインをオンライン テナントから受け入れ、ドメインが一致するようにします。
    - 以前と同じ値になるように、[すべてのエッジ証明書の SAN を更新して](cloud-consolidation-edge-certificates.md)、さらに既存のオンライン SIP ドメイン (*.microsoftonline.com を除く) を加えます。この場合は、Sip.OriginalCompany.<span>com になります。
    - OriginalCompany.<span>com がオンプレミス展開である AcquiredCompany の[許可ドメイン](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain)であることを確認してください。 許可ドメインを追加します。
15. オンプレミスの AcquiredCompany.<span>com とクラウドの間で [Skype for Business Hybrid を有効にします](configure-federation-with-skype-for-business-online.md)。
16. 必要に応じて、[オンプレミスからクラウドにユーザーを移行します](move-users-between-on-premises-and-cloud.md)。 ユーザーの移行は、直接 [[Teams のみ]](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) モードに移行するか、最初に Skype for Business on the web に移行するかのいずれかで実行できます。 この段階では、組織は**[図 D](#figure-d)** のようになります。
17. すべてのユーザーを移行した後、[オンプレミス環境とのハイブリッドを無効にして](cloud-consolidation-disabling-hybrid.md)、*組織を純粋なクラウドにします*。

以下の図面は、このプロセスにおけるさまざまな重要なポイントでの構成を示しています。

##### <a name="figure-a"></a>図 A:

- 両方の組織が AAD Connect を介して同期されるため、AAD には両方のオンプレミス展開のすべてのユーザーが存在しています。
- すべてのユーザーがオンプレミスに所属しています。  
- Skype for Business Hybrid はまだ構成*されていません*。
- いずれかの展開のユーザーが Teams を使用している場合、ユーザーは他のユーザー (または任意の組織) と相互にフェデレーションすることも、Skype for Business ユーザーとの相互運用性を確保することもできません。 この段階では、Microsoft はチャネルでのみ Teams を使用することをお勧めします。<br><br>
    ![図 A の図面](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>図 B:

- AcquiredCompany.<span>com は、[無効な](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)オンライン SIP ドメインです。 すべてのユーザーがオンプレミスに存在しています。 ユーザーが Teams を使用する場合、フェデレーションまたは相互運用性はありません。 この段階では、Microsoft はチャネルでのみ Teams を使用することをお勧めします。
- Skype for Business Hybrid は、オンプレミス組織のいずれかで有効になっています。
- ハイブリッド組織内の一部のユーザーがクラウドに移行されました (紫色の網掛けで示されているユーザー A)。 これらのユーザーは、Skype for Business on the web のユーザーまたは [Teams のみ] のユーザーのいずれかであり、相互運用とフェデレーションに関して完全なサポートを受けることができます。<br><br>
    ![図 B の図面](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>図 C:

- OriginalCompany.<span>com のすべてのユーザーが、クラウドに存在するようになりました (Skype for Business on the web に所属しています)。 これらのユーザーを [Teams のみ] にすることもお勧めします。
- OriginalCompany.<span>com が展開された Skype for Business Hybrid の構成は無効になっています。 オンプレミス展開がなくなりました。
- AcquiredCompany.<span>com が以前に AAD に同期されていなかった場合、ここから続行するには今すぐ同期させる必要があります。 ただし、まだハイブリッド (共有 SIP アドレス スペース) に設定されていません。組織がハイブリッドに移行する準備ができるまで、純粋なオンプレミス組織のオンライン SIP ドメイン (AcquiredCompany.com) を無効のままにして、オンラインの Team ユーザーがオンプレミスのユーザーと通信できるようする必要があります。<br><br>
    ![図 C の図面](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>図 D:

- AcquiredCompany.<span>com がオンライン SIP ドメインとして有効になりました。
- オンプレミスは、OriginalCompany.<span>com を受け入れるように更新されます (許可ドメインとエッジ証明書の両方が更新されます)。
- 共有 SIP アドレス スペースが AcquiredCompany.<span>com と Office 365 テナント間で有効になっています。
- 以下のユーザー D (紫色の網掛けで示されているユーザー) など、ハイブリッド組織の一部のユーザーがクラウドに移行されている可能性があります。<br><br>
    ![図 D の図面](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>その他の開始点

上記の標準的な例の手順では、組織が、Office 365 が存在しない 2 つのフェデレーション オンプレミス展開から開始することを想定しています。 ただし、組織によっては、既存の Office 365 フットプリントがあるため、上述の手順における開始点が異なる場合があります。 一般的な構成は以下の 4 つです。

- Office 365 テナントが存在しない複数のフェデレーション オンプレミス組織。 この場合は、手順 1 から開始します。
- 複数の Skype for Business のフォレストが単一の Azure AD テナントに既に同期されている複数のフェデレーション オンプレミス組織。 このような組織は、図 A に示す仮定の組織のようになります。手順 1 から 6 は完了しているため、手順 7 から開始する必要があります。
- 1 つまたは複数の他の純粋なオンプレミス組織とフェデレーションするハイブリッド組織。いずれも AAD と同期しません。 このような組織は、以下に示す**図 E** の仮定の組織のようになります。
    - この組織は図 B のようになり、手順 1 から 9 は完了しています。ただし、次の点を除きます。
        - 組織の非ハイブリッドの Skype for Business 展開は、まだ Azure AD と同期*していない*。
        -  オンライン SIP ドメインがまだ無効になっていない。 
    - これらの組織は、次のいずれかの操作を行う必要があります。
        - 既存のハイブリッド組織の移行を完了し、上記の手順 10 から開始します。  または、
        - ハイブリッド組織の移行を完了する前にその他の Skype for Business フォレストを AAD に同期する必要がある場合は、組織は手順 7 (AAD と同期するその他のオンプレミス Skype for Business 展開のすべてのオンライン SIP ドメインを無効にする) を実行する必要があります。その後、AAD Connect を有効にして、手順 10 (元のハイブリッド展開の使用を停止する) に進みます。  
                **図 E**<br>
                ![図 E の図面](../media/cloudconsolidationfige.png)
- 独立したオンプレミスの Skype for Business 組織とフェデレーションする純粋な Skype for Business on the web 組織 (Teams を使用している場合もあれば、そうでない場合もあります)。 この組織がオンプレミス組織のオンライン SIP ドメインを無効にして、オンプレミスの Skype for Business 組織の AAD Connect を有効にした場合、この組織は**[図 C](#figure-c)** に示す仮定の組織のようになり、既に手順 1 から 11 は完了しています。

## <a name="limitations"></a>制限事項

- 関係する Office 365 テナントは 1 つでなければなりません。 複数の Office 365 テナントが関係するシナリオでの統合はサポートされていません。
- 一度にハイブリッド モード (共有 SIP アドレス スペース) にできるオンプレミスの Skype for Business フォレストは 1 つのみです。 それ以外のすべてのオンプレミスの Skype for Business フォレストは純粋なオンプレミスのままにして、フォレスト同士および Office 365 テナントとフェデレーションする必要があります。
- クラウドに移行する前は、この展開に存在するユーザーのエクスペリエンスは非対称です。これは、オンラインのすべてのユーザーがオンプレミスで表されるわけではないためです。
    - エクスペリエンスを要約すると次のようになります。
        - オンラインに所属しているユーザーは、自分がハイブリッド ユーザーであるかのようにハイブリッド環境のオンプレミス ユーザーと対話する。
        - ハイブリッド展開のオンプレミス ユーザーは、オンプレミス ディレクトリに表されているオンライン ユーザーをハイブリッド ユーザーであるかのように扱って対話する。 
        - ハイブリッド展開のオンプレミス ユーザーは、オンプレミス AD に表されていないオンライン ユーザーをフェデレーション ユーザーであるかのように扱って対話する。
    - 上記の**[図 D](#figure-d)** では、ユーザー E は AcquiredCompany.<span>com のオンプレミス ユーザーです。  ユーザー E は、標準のハイブリッド エクスペリエンスを使用して、ユーザー D (オンラインに所属) と対話しますが、ユーザー E はユーザー A、B、C とフェデレーションされます。これは、ユーザー A、B、C がオンプレミス ディレクトリに表されないためです。 ただし、ユーザー A、B、C は、ユーザー E をハイブリッド ユーザーであるかのように扱って対話します。
    - ハイブリッドとフェデレーション間の相互作用による影響
        - フェデレーション ユーザーのプレゼンスは、ユーザーが連絡先としてマークされている場合を除き、自動的に登録されることはありません。
        - 着信転送はフェデレーション ドメイン間では機能しません。
        - 通話転送のシナリオには多くの制限があります。
        - フェデレーション トラフィックに調整を適用できます。
- この非対称なエクスペリエンスでは、オンプレミス ユーザーとオンプレミス ディレクトリに含まれていないクラウド ユーザー間では、クロスプレミス シナリオの通話機能に対する公式なサポートはピア ツー ピアのみに制限されています。 
    - これらのユーザー間における着信転送、通話転送、通話キューなどは、サポートされていません。
    - これらのサポートされていない通話のシナリオは引き続き有効のように見えますが、多くの場合、予期しない動作が発生して失敗します。 
    - 上記の**[図 D](#figure-d)** では、ユーザー E はオンプレミス ユーザーであり、ユーザー A、B、C との通話はピア ツー ピアとしてのみサポートされます (ユーザー D との通話のサポートには制限はありません)。ただし、オンプレミス ユーザー E をクラウドに移行すると、この制限は適用されなくなります。
- お使いの環境で Skype for Business Server 2019 の展開が複数ある場合、組織自動アテンダントを使用するように構成できる展開はそのうちの 1 つだけです。これは、その機能には Skype for Business Server Hybrid 構成が必要なためです。 
- 前の手順の順序は一部調整できます。 そのためには、次のすべての条件に当てはまる必要があります。
    - 1 つの AAD テナントに同期するオンプレミスの Skype for Business フォレストが複数ある
    - 分割ドメインが 1 つのオンプレミス フォレストで有効になっている
    - ハイブリッド組織内の少なくとも 1 人のユーザーがクラウドに移行されている<br>   その後、その他のオンライン SIP ドメインを他のオンプレミスの Skype for Business フォレストですべて無効にする*必要があります*。 無効にしないと、ハイブリッド組織のオンライン ユーザーとそれ以外の組織のオンプレミス ユーザー間のフェデレーションが一方向で中断されます。

## <a name="implications"></a>影響

- 上記で説明したように、高度な通話機能のサポートには制限があるため、**組織はこのような非対称な状態を移行の一環として一時的なものとして扱い、安定状態として追求する必要はありません**。  
- 一般的に、オンプレミスの Skype for Business の展開が複数ある組織は、クラウドに完全に移行できる展開を使用して開始し、統合を継続することができます。 場合によっては、Teams にまだ移行することができない特定のユーザー グループのホールドアウトが発生します。 複数の Skype for Business フォレストが関係するシナリオでこれを考慮する場合は、可能な限り、これらの制限がない別のフォレストを使用して移行を開始します。
- オンプレミスからクラウドに移行する場合、委任関係のあるユーザーや通常は着信転送シナリオに関係するユーザーは、1 つの単位として一緒に移行させる必要があります。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>[Teams のみ] モードに移行する場合の考慮事項

オンプレミスからのハイブリッド環境のクラウドにユーザーを移行する場合は、[Skype for Business のみ] モードまたは [Teams のみ] モードのいずれかに移行できます。 *ユーザーを [Teams のみ] モードに移行する場合は、初めにこのセクションをお読みください。*

- [Teams のみ] モードをユーザーに割り当てると、他のユーザーからのチャットと通話はすべて、そのユーザーの Teams クライアントに届きます。 
- オンプレミスの Skype for Business を使用しているユーザーが Teams ではなく、主に Skype for Business クライアントを使用している場合は、これらのオンプレミス ユーザーへのルーティングが Teams ではなく Skype for Business に常に届くように TeamsUpgradePolicy を設定することを検討してください。 [Teams のみ] のユーザーと引き続きオンプレミスの Skype for Business を使用しているユーザー間でチャットと通話を適切にルーティングするには、オンプレミス ユーザーに [アイランド] モード (既定値) ではなく、いずれかの SfB モードで有効な TeamsUpgradePolicy の値が設定されている必要があります。 
    - これを行うには、*まず TeamsUpgradePolicy のテナントのグローバル インスタンスを次の値のいずれかに設定する必要があります*。
        - SfBWithTeamsCollab (推奨)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 次のコマンドを使用して、テナント全体のポリシーを付与できます。<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 注: オンライン ディレクトリの SIP アドレスがない個々のユーザーにはポリシーを割り当てることはできないため、テナント全体レベルでこの手順を実行する必要があります。 純粋なオンプレミス展開ではオンライン SIP ドメインを無効にしていますが、それらのドメインのユーザーには、オンライン ディレクトリの SIP アドレスがありません。これは意図した仕様です。 そのため、オンプレミス ユーザーにポリシーを適用するには、テナント レベルで割り当てる方法しかありません。 一方、ハイブリッド展開では、ユーザーはオンライン ディレクトリの SIP アドレスがあるため、ユーザーがテナントのグローバル ポリシーとは異なる値を必要とする場合、明示的にポリシーを割り当てることができます。
- Teams クライアント UX では、TeamsUpgradePolicy の SfB モードはまだ優先されません。 たとえば、これらのモードでは、現在 Teams で通話とチャットを開始できますが、将来的にはできなくなります。 状況によって返信が Teams に届いたり、Skype for Business に届いたりすることがあるため、ユーザー間で混乱が生じる可能性があります。 引き続きオンプレミスを使用しているユーザーは、TeamsMessagingPolicy と TeamsCallingPolicy を介して通話とチャットを個別に無効にすることをお勧めします。

## <a name="see-also"></a>関連項目

[エッジ証明書の更新](cloud-consolidation-edge-certificates.md)

[AAD Connect を更新して複数のフォレストを含める](cloud-consolidation-aad-connect.md)

[ハイブリッドを無効にしてクラウドへの移行を完了する](cloud-consolidation-disabling-hybrid.md)
