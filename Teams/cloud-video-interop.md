---
title: Microsoft Teams のクラウド ビデオ相互運用性
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Cloud Video Interop を中間ソリューションとして使用して、サードパーティの会議室デバイスが会議に参加Microsoft Teamsします。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39452a659f1a95d66aeac4a18a4d7801764437ae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618643"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams のクラウド ビデオ相互運用性

クラウド ビデオ相互運用性 (CVI) は、サード パーティ製の会議室 (テレプレゼンス) と個人用ビデオ デバイス (VTC) が Microsoft Teams の会議に参加できるようにする Microsoft 認定のサード パーティ ソリューションです。
 
Microsoft Teams を使用すると、音声、ビデオ、およびコンテンツ共有を含む会議で、豊富なオンライン コンテンツ コラボレーションを実現できます。 これは、デスクトップと Web クライアントだけでなく、Microsoft Teams とネイティブに統合された多くのパートナー デバイスでも楽しむことができます。 しかし、多くのお客様がアップグレードに費用がかかるかもしれないビデオ会議デバイスや個人用ビデオ通信デバイスに既に投資しています。 クラウド ビデオ相互運用性は簡単なソリューションを提供し、アップグレードの準備が整うまで既存のソリューションを使用し続けることができます。

Microsoft Teams は、クラウド ビデオ相互運用性により、会議室または Teams のクライアントで、すべての参加者にネイティブな会議エクスペリエンスを提供します。

### <a name="is-cloud-video-interop-for-me"></a>クラウド ビデオ相互運用性は私に適していますか?

クラウド ビデオ相互運用性は、Teams エンドポイントを使用して完全なネイティブ Microsoft Teams ソリューションに移行する際に中間サービスを提供します。 提供されるサービスは、移行パスに含まれている必要があります。

クラウド ビデオ相互運用性は、次の条件を満たす顧客を対象としています。

- Microsoft Teams との直接統合が認められていない会議室デバイスおよび個人用 ビデオ デバイス (50 台以上) を大規模に展開する
- クラウド ビデオ相互運用性パートナーのいずれかによってサポートされている
- ネイティブの Microsoft Teams ソリューションへの移行時に、現在の会議室デバイスおよび個人用ビデオ デバイスへの投資価値を維持したい

クラウド ビデオ相互運用性は優れた中間ソリューションを提供しますが、Teams ミーティング システムなどのネイティブの Teams Meeting ソリューションを長期的に使用するために、検討することをお勧めします。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365米国政府とサード パーティのサービス

Office 365 では、Microsoft 365 Apps for enterprise に含まれる SharePoint Online サイト、Skype for Business、Teams、Office、Office アプリケーション (Word、Excel、PowerPoint、Outlook など) にサード パーティ製アプリケーションを統合Outlook Web App。 さらに、Office 365サード パーティのサービス プロバイダーとの統合をサポートしています。 これらのサード パーティ製のアプリケーションとサービスには、Office 365 インフラストラクチャの外部にあるサードパーティ システム上で組織の顧客データを格納、送信、処理する必要があります。そのため、Office 365 のコンプライアンスとデータ保護のコミットメントの対象外となります。 **お客様の組織に対するこれらのサービスの適切な使用を評価する際には、第三者から提供されるプライバシーおよびコンプライアンスに関する声明を確認してください。**



### <a name="partners-certified-for-microsoft-teams"></a>Microsoft Teams 認定パートナー

次のパートナーには、Microsoft Teams のビデオ相互運用性ソリューションがあります。 企業は、企業内でこれらのパートナーのいずれかと組み合わせて使用することを選択できます。 

|パートナー|パートナー ソリューション|
|----|---|
|![Poly RealConnect を表すロゴ](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect サービス</a> |
|![Pexip Infinity を示すロゴ](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a> | 
|![BlueJeans Gateway を示すロゴ](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a> |
|![Cisco CVI を表すロゴ](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>クラウド ビデオ相互運用性の概要

クラウド ビデオ相互運用性は、既存のオンプレミスのビデオ会議と個人用ビデオ デバイス ソリューション、および Microsoft Teams 間の相互運用性を提供するサード パーティ サービスです。

パートナーが提供するソリューションは、完全なクラウド ベースまたは部分的に/完全にオンプレミスに展開できるコンポーネントで構成されています。 
     
次の図は、パートナー ソリューションのアーキテクチャの概要を示しています。

![Teams のクラウド ビデオ相互運用性パートナー ソリューションを説明する図](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>クラウド ビデオ相互運用性を展開する

Cloud Video Interop ソリューションをデプロイする場合は、パートナー ソリューションをデプロイしている点を理解することが重要です。 クラウド ビデオ相互運用性を展開するために必要な一般的な手順を次の図に示します。

![組織での CVI の展開を説明する図](media/deploying-cvi.png)

### <a name="plan"></a>計画

計画フェーズでは、ネイティブの Teams デバイスと交換しないデバイスを特定し、これらのデバイスをサポートできるクラウド ビデオ相互運用性パートナーを見つける必要があります。  

また、Cloud Video Interop 対応デバイスを参加する会議をスケジュールする各ユーザーのライセンスが必要な点も理解することが重要です。 正確なライセンス要件は、クラウド ビデオ相互運用性パートナーから取得できます。 展開を開始する前に、ライセンスに関することがクリアされていることを確認してください。

### <a name="configure"></a>構成

CVI 展開用に選択したパートナーは、組織内で正常に展開するために必要なすべての手順が含まれている完全な展開ドキュメントを提供します。 これには、ファイアウォール ポートと IP 範囲、デバイスの構成変更、およびその他の変更が必要な設定が含まれます。

### <a name="provision"></a>プロビジョニング  

プロビジョニング フェーズでは、パートナーから提供された構成ガイドに従って、適切なユーザーにライセンスを割り当てます。 また、パートナーが Teams 環境にアクセスできるようにするには、Azure 同意プロセスも実行する必要があります。 Azure[の同意プロセスの詳細については、「Microsoft ID プラットフォーム エンドポイント](/azure/active-directory/develop/v2-permissions-and-consent)のアクセス許可と同意」を参照してください。

### <a name="schedule"></a>スケジュール

ユーザーがクラウド ビデオ相互運用性を有効にすると、Outlook または Teams クライアン トの Teams 会議アドインを使用してスケジュールされたすべての会議に、適切な追加情報が自動的に追加されるため、クラウド ビデオ相互運用性デバイスをこれらの会議に使用できるようになります。

### <a name="join"></a>参加

パートナー ソリューションによっては、クラウド ビデオ相互運用性対応の会議に参加する方法がいくつかあります。 正確な会議参加シナリオは、クラウド ビデオ相互運用性パートナーから提供されます。 以下に例を示します。

- IVR (対話型音声応答) 
  - tenantkey@domain を使用して、パートナーの IVR にダイヤルインできます。
  - パートナー IVR にいると、VTC conferenceId を入力するように求められます。これにより、Teams 会議に接続されます。
- 直接ダイヤル 
  - テナント キーの完全な文字列を使用して、パートナーの IVR と対話することなく、Teams 会議に直接ダイヤルインできます。VTC ConferenceId@domain。
- ワンタッチ ダイヤル 
  - Teams ミーティングが統合されている場合は、パートナーが提供するワンタッチ ダイヤル機能を使用できます (ダイヤルの文字列を入力する必要はありません)。

## <a name="manage-cloud-video-interop"></a>クラウド ビデオ相互運用性の管理

クラウド ビデオ相互運用性の展開後、パートナーが提供するソリューションを使用してデバイスを管理できます。 各パートナーは、ライセンスとデバイス管理の両方を含む管理インターフェイスを提供します。 

レポートは、パートナーの管理インターフェイスから直接使用することもできます。 レポート機能の詳細については、選択したパートナーにお問い合わせください。 

### <a name="troubleshooting-cloud-video-interop"></a>クラウド ビデオ相互運用性のトラブルシューティング

クラウド ビデオ相互運用性は、パートナーが提供するサービスです。 問題が発生した場合は、まず Teams クライアントがインストールされているデバイスを接続し、問題の原因となっているクラウド ビデオ相互運用性デバイスと同じセグメントに接続します。 

このセグメントで Teams が正しく機能し、パートナーが提供したすべてのネットワークおよび構成ガイドラインにも従っている場合は、トラブルシューティングについてパートナーに連絡する必要があります。 

## <a name="powershell-for-cloud-video-interop"></a>クラウド ビデオ相互運用性のための PowerShell

クラウド ビデオ相互運用性の展開を (部分的に) 自動化するには、次の PowerShell コマンドレットを使用します。

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft は、サポート対象の各パートナーに対して、クラウド ビデオ相互運用性に使用するパートナーを指定できる事前構築ポリシーを提供しています。<br>このコマンドレットは、組織内で使用できる事前構築ポリシーを指定できます。 Grant-CsTeamsVideoInteropServicePolicy コマンドレットを使用して、このポリシーを 1 人または複数のユーザーに割り当てることができます。
- **Grant-CsTeamsVideoInteropServicePolicy**: このコマンドレットを使用すると、組織で使用するために事前構築されたポリシーを割り当てたり、特定のユーザーにポリシーを割り当てることができます。
- **New-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織が使用するサポート対象の CVI パートナーに関する情報を指定します。
- **Set-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織が使用するサポート対象の CVI パートナーに関する情報を更新します。
- **Get-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織内で使用するように構成されているすべてのプロバイダーを取得します。
- **Remove-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織で使用しなくなったプロバイダーに関するすべてのプロバイダー情報を削除します。