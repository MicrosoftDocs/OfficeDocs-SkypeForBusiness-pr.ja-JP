---
title: Teams Geo 対応環境Microsoft 365環境でのエクスペリエンスの向上
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: この記事では、複数の geo 対応環境でTeamsをMicrosoft 365について学習します。
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760540"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams Geo 対応テナントMicrosoft 365でのエクスペリエンスの向上

Microsoft Teamsは、グループ チャット ソフトウェアであり、チームワークのハブであり、Microsoft 365およびOffice 365。 Microsoft 365 Groups サービスを利用し、SharePoint Online とOneDrive for Businessファイルエクスペリエンスを提供します。 テナントが北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張される OneDrive for Business/SharePoint Online Multi-Geo テナントでは、基になるファイル エクスペリエンスはマルチ geo 対応なので、Teams でのファイルコラボレーションのエクスペリエンスもマルチ geo 対応です。 この機能は、ネイティブ ファイル エクスペリエンスでTeams Geo でホストされているファイルを表示するための主要な最先端の機能です。 これには、他のOneNote Wiki ファイルも含まれます。

たとえば、ヨーロッパを衛星 geo として、北米を中央 Geo として使用する Contoso テナントでは、ヨーロッパの衛星ユーザーは左側のウィンドウの [ファイル] タブに OneDrive ファイルを表示しますが、ファイルはヨーロッパのデータの場所でホストされ、米国はテナントの中央の場所です。 また、ユーザーは [最近使用したビュー] ブレードで、最近使用した **ファイルに** アクセスできます。 最近使用したファイルには、他の地理的な場所のユーザーから共有されたファイルが含まれる場合があります。 

特定のチームのSharePointサイトもマルチ geo 対応です。 つまり、ヨーロッパの衛星ユーザーがチームを作成している場合、対応するSharePointサイトがヨーロッパの場所に作成されます。 そのチームに関連付けられているファイルは、その場所に保存されます。 新しいファイルのアップロードやファイルの編集などの後続のエクスペリエンスは、ヨーロッパの場所に保存され、それらのファイルのデータ常駐が約束されます。

Multi-Geo テナントは 1 つのグローバル テナントなので、@ メンション中は、衛星ユーザーは、場所に関係なく、世界中から同僚を表示できます。

Teams エクスペリエンス内のチャット、チャネル メッセージ、会議 IM ノート/チャットの会話は、マルチ geo 対応ではなんらテナントの中央の場所内にのみ保持されます。 通常、チャット会話はデータ常駐のニーズには適用されません。 詳細については、「データの場所[」を参照Microsoft Teams。](location-of-data-in-teams.md)

複数地域でのサポートは、Teamsロードマップ[Microsoft 365されています](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)。

Multi-Geo の詳細については [、Microsoft Multi-Geo の機能に関するページを参照してください](https://aka.ms/multi-geo)。
