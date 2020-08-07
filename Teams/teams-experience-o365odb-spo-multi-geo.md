---
title: Microsoft 365 または Office 365 OneDrive および SharePoint Online の複数の地域に対応したテナントでの Teams の操作
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: この記事では、Microsoft 365 または Office 365 OneDrive と SharePoint Online の複数の Geo 対応のテナントで Teams を使用する方法について説明します。
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
ms.openlocfilehash: 1fdfd99494b8f65c448a2b1183a183b8cf7477af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583244"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Microsoft 365 または Office 365 OneDrive および SharePoint Online の複数の地域に対応したテナントでの Teams の操作
===========================================

Microsoft Teams は、グループチャットソフトウェアであり、Microsoft 365 および Office 365 でのチームワークのハブです。 この機能は、Microsoft 365 Groups サービスと SharePoint Online および OneDrive for Business のファイルエクスペリエンスによって実現されています。 OneDrive for Business または SharePoint Online の複数地域のテナント (北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所にテナントが拡張されているため、基盤となるファイルのエクスペリエンスは複数の地域に対応しているため、ファイルの共同作業でも複数の地域に対応しています。 これは、ネイティブファイルエクスペリエンスで複数の Geos でホストされているファイルを処理するための主要な最先端機能です。

たとえば、ヨーロッパを使用する Contoso のテナントが、中央の Geo としてサテライトの Geo および北米として表示されている場合、ファイルはヨーロッパのデータの場所でホストされていますが、米国はテナントの中央の場所であるということです。 また、最新のビューブレードで、最近使用したファイルにアクセスすることもできます。 最近使用したファイルには、他の Geos のユーザーから共有されているファイルが含まれている可能性があります。また、テナントが拡張されている他の Geo の場所でもそのようになっている場合 

特定のチームのグループサイトも、複数の地域に対応しています。 つまり、ヨーロッパのサテライトユーザーがチームを作成している場合、対応するグループサイトはヨーロッパの場所に作成され、そのチームグループに関連付けられたファイルは、その場所の残りの部分に保存されます。 新しいファイルをアップロードしたり、ファイルを編集したりするなど、以降のすべてのエクスペリエンスは、そのヨーロッパの場所を対象としているため、これらのファイルに対してデータを確実に保持できます。 これは、基本的な foundation Microsoft 365 グループによって、複数の地域に対応するようになりました。

複数の Geo のテナントは1つのグローバルテナントであるため、@ メンションを実行しているユーザーは、どこにいても、世界中の同僚を見ることができます。 

チームエクスペリエンス内でのチャットおよび会議 IM のメモの会話は、複数の地域に認識されず、すべてがテナントの中央の場所でのみ保持されることに注意してください。 通常、チャットの会話はデータ常駐のニーズには適用されません。

複数地域の詳細については、「 [Microsoft の多機能機能」ページ](https://aka.ms/multi-geo)を参照してください。