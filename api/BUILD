#
# GRAKN.AI - THE KNOWLEDGE GRAPH
# Copyright (C) 2018 Grakn Labs Ltd
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as
# published by the Free Software Foundation, either version 3 of the
# License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
#
#
package(default_visibility = [
    "//server:__pkg__",
    "//client:__pkg__",
    "//test-integration/rule:__pkg__", # TODO: remove this once we move GraknTestServer in //server/test
    # TODO: expose this package to "@graknlabs_grakn_kgms//server:__subpackages__"
])

load("//dependencies/maven:rules.bzl", "deploy_maven_jar")
load("//dependencies/tools/checkstyle:checkstyle.bzl", "checkstyle_test")

java_library(
    name = "api",
    srcs = glob(["**/*.java"]),
    deps = [
        "//concept:concept",
    ],
    tags = ["maven_coordinates=grakn.core:api:{pom_version}"],
)


deploy_maven_jar(
    name = "deploy-maven-jar",
    target = ":api",
    package = "api",
)

checkstyle_test(
    name = "checkstyle",
    targets = [
        ":api"
    ],
)