---
title: Microsoft Teams のクラウド ビデオ相互運用性
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: クラウドビデオ相互運用機能を利用すると、サードパーティの会議室デバイスが Microsoft Teams 会議に参加できるようになります。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d37acef498abfd0ed3e9125529abef38f737406
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237073"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams のクラウド ビデオ相互運用性

クラウドビデオ相互運用機能 (CVI) は、microsoft Teams 会議に参加するためのサードパーティの会議室 (テレプレゼンス) と個人用ビデオデバイス (VTCs) を可能にする、Microsoft 認定のサードパーティソリューションです。
 
Microsoft Teams を使用すると、オーディオ、ビデオ、コンテンツの共有を含む、豊富なオンラインコンテンツコラボレーションを会議で利用できます。 これは、デスクトップと web クライアント、および Microsoft Teams とネイティブに統合されている多くのパートナーデバイスを通じて利用することができます。 ただし、多くのお客様は、すでにビデオ会議や個人のビデオ通信デバイスに投資していますが、アップグレードにはコストがかかる場合があります。 クラウドビデオの相互運用機能により、簡単な解決方法が提供されるため、アップグレードの準備ができたら、既存のソリューションを引き続き使用できます。

クラウドビデオの相互運用機能を使用すると、Microsoft Teams がすべての参加者に対してネイティブな会議エクスペリエンスを提供します。会議室または Teams クライアントの内部で行います。

### <a name="is-cloud-video-interop-for-me"></a>クラウドビデオの相互運用機能

クラウドビデオ相互運用機能は、チームのエンドポイントを使用して、完全なネイティブの Microsoft Teams ソリューションに移行しながら、中間的なサービスを提供します。 提供されるサービスは、移行パスの一部である必要があります。

クラウドビデオの相互運用機能は、次の条件を満たしているお客様を対象としています。

- Microsoft Teams との直接統合が認められていない、会議室デバイスと個人用ビデオデバイスの展開 (50 以上のデバイス) の大規模な展開を行う
- は、クラウドビデオの相互運用パートナーのいずれかでサポートされています。
- Microsoft Teams のネイティブソリューションへの移行中に、現在の会議室のデバイスと個人用のビデオデバイスで投資の金額の値を保持する

クラウドビデオ相互運用機能は、優れた中級ソリューションを提供していますが、お客様は長期のチームルームシステムなどのネイティブのチーム会議ソリューションを参照することをお勧めします。 

### <a name="partners-certified-for-microsoft-teams"></a>Microsoft Teams の認定パートナー

次のパートナーには、Microsoft Teams のビデオ相互運用ソリューションが用意されています。 会社では、企業内でこれらのパートナーの任意の組み合わせを使用することができます。 

|パートナー|パートナーソリューション|
|----|---|
|![Polycom RealConnect を表すロゴ](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect サービス</a> |
|![Pexip 無限大を表すロゴ](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams の Pexip 無限大</a> | 
|![BlueJeans Gateway を表すロゴ](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams の BlueJeans ゲートウェイ</a> |

### <a name="cloud-video-interop-overview"></a>クラウドビデオの相互運用の概要

クラウドビデオ相互運用機能は、社内のビデオ会議と、オンプレミスのビデオデバイスソリューション、および Microsoft Teams との相互運用性を実現するために、パートナーが提供するサードパーティサービスです。

パートナーが提供するソリューションは、完全なクラウドベースまたは一部/すべてのオンプレミスのいずれかに展開できるコンポーネントで構成されます。 
     
次の図は、パートナーソリューションの上位レベルのアーキテクチャを示しています。

![Teams Cloud ビデオの相互運用性パートナーソリューションについて説明する図](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>クラウドビデオの相互運用機能を導入する

クラウドビデオ相互運用ソリューションを展開するときは、パートナーソリューションを展開することを理解しておくことが重要です。 クラウドビデオの相互運用機能を展開するための一般的な手順を次の図に示します。

![組織での CVI の展開について説明した図](media/deploying-cvi.png)

### <a name="plan"></a>計画

計画フェーズでは、ネイティブの Teams デバイスと置き換えることができないデバイスを特定し、これらのデバイスをサポートできるクラウドビデオの相互運用パートナーを見つけます。  

また、クラウドビデオ相互運用対応デバイスを参加させる会議をスケジュールするユーザーごとに、ライセンスが必要であることを理解しておくことも重要です。 正確なライセンス要件は、クラウドビデオの相互運用パートナーから入手できることに注意してください。 展開を開始する前に、これが明確であることを確認します。

### <a name="configure"></a>構成

CVI 展開用に選択したパートナーには、組織内で正常に展開するために必要なすべての手順で構成される完全な展開ドキュメントが提供されます。 これには、ファイアウォールポートと IP 範囲、デバイスの構成の変更、変更が必要なその他の設定が含まれます。

### <a name="provision"></a>規定  

プロビジョニングフェーズでは、パートナー構成ガイドに従ってライセンスを適切なユーザーに割り当てます。 また、Azure の同意プロセスに従って、パートナーのアクセスをチーム環境に提供する必要があります。 Azure 同意プロセスの詳細については、次のページを参照してください。https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>基点

クラウドビデオ相互運用機能が有効になった後、[Teams 会議] アドインを使用して予定されている Outlook または Teams クライアントでは、適切な追加情報が Teams 会議に自動的に追加されるため、クラウドビデオを利用することができるようになります。相互運用対応デバイスは、これらの会議に参加できます。

### <a name="join"></a>Join

パートナーソリューションによっては、クラウドビデオ相互運用対応の会議に参加するには、いくつかの方法があります。 会議の正確な参加シナリオは、クラウドビデオの相互運用パートナーによって提供されます。 以下に例をいくつか示しました。

- IVR (インタラクティブな音声応答) 
  - Tenantkey @ domain を使って、パートナーの IVR にダイヤルインすることができます。
  - パートナー IVR を使用している場合は、VTC conferenceId を入力するように求められます。これにより、Teams の会議に接続されます。
- ダイレクトダイヤル 
  - このダイレクトダイヤル機能を使用すると、パートナーの IVR とやり取りすることなく、直接、tenantkey の完全な文字列を使用して、Teams 会議に直接ダイヤルインすることができます。VTC ConferenceId @ domain
- ワンタッチダイヤル 
  - 統合されたチームルームがある場合は、パートナーが提供するワンタッチダイヤル機能を使用できます (ダイヤル文字列を入力する必要はありません)。

## <a name="manage-cloud-video-interop"></a>クラウドビデオの相互運用機能を管理する

クラウドビデオ相互運用機能を展開した後は、パートナーが提供するソリューションを使用してデバイスを管理することができます。 各パートナーには、ライセンスとデバイスの管理の両方を含む、管理インターフェイスが用意されています。 

レポートは、パートナー管理インターフェイスから直接利用することもできます。 レポート機能の詳細については、お好みのパートナーにお問い合わせください。 

### <a name="troubleshooting-cloud-video-interop"></a>クラウドビデオの相互運用のトラブルシューティング

クラウドビデオ相互運用機能はパートナーが提供するサービスです。 問題が発生した場合は、最初の手順として、Teams クライアントがインストールされているデバイスを接続して、問題の原因となっているクラウドビデオ相互運用デバイスと同じセグメントに接続します。 

Teams がこのセグメントで正しく機能し、パートナーが提供したすべてのネットワークと構成のガイドラインも順守されている場合は、さらにトラブルシューティングのためにパートナーに連絡する必要があります。 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell for Cloud Video Interop

次の PowerShell コマンドレットを使用して、クラウドビデオ相互運用機能の展開を自動化することができます (部分的な場合)。

- **CsTeamsVideoInteropServicepolicy**: サポートされているパートナーのそれぞれに対して事前構築されたポリシーを提供します。これにより、クラウドビデオ相互運用に使用するパートナーを指定することができます。<br>このコマンドレットでは、組織で使用できる事前構築済みのポリシーを識別できます。 このポリシーは、Grant-CsTeamsVideoInteropServicePolicy コマンドレットを利用して、1人以上のユーザーに割り当てることができます。
- **Grant-CsTeamsVideoInteropServicePolicy**: このコマンドレットでは、組織で使用するために事前構築されたポリシーを割り当てることができます。または、特定のユーザーにポリシーを割り当てることもできます。
- **新規-CsVideoInteropServiceProvider**: 組織で使用したいサポートされている cvi パートナーに関する情報を指定するには、このコマンドレットを使用します。
- **Set-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織が使用しているサポートされている cvi パートナーに関する情報を更新します。
- **Get-CsVideoInteropServiceProvider**: 組織内で使用するように構成されているすべてのプロバイダーを取得するには、このコマンドレットを使用します。
- **Remove-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織で使用されなくなったプロバイダーに関するすべてのプロバイダー情報を削除します。
