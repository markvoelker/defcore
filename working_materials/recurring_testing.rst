==============================
Recurring Testing Requirements
==============================

Problem Statement
=================

The OpenStack Foundation currently requires that vendors submit to annual
testing against DefCore Guidelines in order to obtain and maintain a legal
license to use the OpenStack Powered logo and OpenStack trademark.  The
general idea is that vendors should be required to maintain versions of
their products that meet modern DefCore criteria in the interest of
end users being assured of their committment to interoperability.  There are
currently some other issues in the contract requirements, which has sparked
a broader discussion about how to handle recurring testing.  The end
goal is to create a recurring testing schema which provides consumers of
OpenStack Powered(TM) products with good assurance that the products
they have to choose from are interoperable, while not putting reasonable
requirements on vendors that don't pose an undue burden.

This document attempts to lay out the current thinking of the DefCore
Committee around the types of annual testing we think is advisable.  This
document is considered nonbinding until approved by the OpenStack Foundtion
itself, which holds the right to issue the license agreements.

Use Cases
=========

The usefullness of recurring testing is somewhat different based on the type
of product being offered.  Therefore it is important to take several use cases
into account.  The key considerations we will examine below are when the vendor
releases updates or upgrades that have reasonable potential to break interoperability,
and the degree to which customers have the ability to control when new code is
deployed.

The use cases below attempt to be illustrative and are not considered comprehensive.

OpenStack Distributions
-----------------------

OpenStack distributions are loosely defined as software bundles that consumers
install on their own infrastructure and operate as they see fit.  Generally,
distributions place some requirements on the infrastructure (for example,
minimum CPU/RAM/storage requirements, minimal node counts, etc) and may provide
support for only a subset of all available OpenStack configurations and backends.
Distributions tend to ship new major releases on a periodic basis: for example,
many distributions ship one or two major releases per year in order to stay in
cadence with the upstream community releases.  Consumers of OpenStack distributions
typically have full control over when they choose deploy new versions of
the software (major releases or maintenance patches).  They may choose to deploy
a new version as soon as it is released, or they may wait for considerable periods
of time before deploying.  Maintenance patches are generally thought to be
unlikely to intentionally disable DefCore-required Capabilities, and users generally
have the opportunity to test the new software before deploying it to production.

Because of the periodic nature of distribution releases and the ability of the
customer to choose the deployment timetable, periodic testing of the product is
potentially a reasonable path to take.  Vendors of distributions might be required
to test against their most currently available product against either of the two
most current Board-approved DefCore Guidelines either once per year or once per
major release, whichever is more frequent.  If the distribution issues periodic
maintenance releases, retesting on those maintenance releases is encouraged
but not required (since in most known cases, maintenance releases are unlikely
to affect required capabilities and since customers have the ability to test
them and adopt them on their own timetables).

Similar timetables might well apply to other products that have similar
characteristics to distributions: for example some OpenStack appliances ship
as physical device (or set of devices) that the customer administers and can
choose to upgrade software releases on at a time of their choosing.  Such
products would follow the same timeline as distributions.  Some managed products
include both software and and ongoing operational support of that software, but
customers retain the right to choose when upgrades of the software occurs.
Such products would also follow the same timeline as distributions.

Public Clouds
-------------

Public clouds are generally characterized as services on which customers have
no direct ownership of resources, but rather rent capacity from an existing
resource pool.  In public cloud environments, customers do not have any control
over the OpenStack control plane, and can generally only perform tenant operations.
Customers also therefore have no control over when the OpenStack software they
are using receives updates or upgrades: that timetable is controlled by the
cloud provider, who may or may not give notice of software changes rolling out.
Some public cloud providers push updates to their software several times per day
or several times per week without end-user intervention or notification for
minor maintenance.  

Annual testing requirements for public clouds may not provide much assurance to
consumers that the product will remain interoperable since customers do not
control when the software changes or have the ability to test the new software
before adopting it.  Recurring testing is therefore needed more frequently for
public cloud products.  A suggested timeframe is once every four weeks.  Public
cloud vendors are encouraged to encorporate testing directly into their
CI/CD systems if possible to provide an even higher assurance to their customers
that the product remains interoperable at all times.

Similar timetables might well apply to other products that have similar
characteristics to public clouds.  For example, some hosted private clouds
and managed private clouds do not allow customers to choose when software is
updated or allow them to perform acceptance testing in advance, because
operational service of the cloud is considered part of the product.  Similarly,
some appliance products automatically update their OpenStack software on a
basis that is not controlled by the end user.  Such products would follow the
same recurring testing timeframes as public clouds.

Recommendations
===============

The DefCore Committee recommends one of two schedules be applied to OpenStack
Powered(TM) products based on how they self-identify when applying for a
trademark/logo license agreement.  

Schedule A
----------
* Applies to products in which the customer maintains control over when the
  OpenStack software is changed in their environment and has reasonable ability
  to perform acceptance testing first.
* Generally includes distributions, appliances, and some managed products.
* Requires that the most recent generally available version of the product pass
  all tests specified in either of the two most recent DefCore Guidelines approved
  by the Board of Directors on an annual basis or with every major software
  release, whichever is more frequent.
* The annual testing requirement will be determined by the date on which both
  the OpenStack Foundation and the vendor signed the last license agreement.
* When feasible, it is recommended but not required that vendors test each maintenance
  release of their products as well.  To encourage this behavior, the Foundation
  will reset the clock on the annual testing requirement to the date on which the
  Foundation verifies that a maintenance release has passed testing.

Schedule B
----------
* Applies to products in which the customer does not control the schedule on
  which the OpenStack software is deployed and cannot reasonably conduct acceptance
  testing before the change is deployed.
* Generally includes public clouds, some managed products, and some appliances.
* Requires that the most recent generally available version of the product pass
  all tests specified in either of the two most recent DefCore Guidelines approved
  by the Board of Directors once every four weeks.
* The start date of the four-week period will be determined by the date on which
  the OpenStack Foundation and the vendor signed the last license agreement.
* When feasible, it is recommended but not required that vendors test each
  maintenance release of their software as well.  To encourage this behavior, the
  Foundation will reset the clock on the four-week testing period to the date on
  which the Foundation verifies that a maintenance release has passed testing.
