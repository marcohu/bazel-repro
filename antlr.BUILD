package(default_visibility = ["//visibility:public"])

genrule(
    name = "grammars",
    srcs = [
        "tool/src/main/antlr3/org/antlr/grammar/v3/ActionAnalysis.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/ActionTranslator.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/ANTLR.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/ANTLRTreePrinter.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/ANTLRv3.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/AssignTokenTypesWalker.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/CodeGenTreeWalker.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/DefineGrammarItemsWalker.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/LeftRecursiveRuleWalker.g",
        "tool/src/main/antlr3/org/antlr/grammar/v3/TreeToNFAConverter.g",
    ],
    outs = [
        "org/antlr/grammar/v3/ActionAnalysis.java",
        "org/antlr/grammar/v3/ActionTranslator.java",
        "org/antlr/grammar/v3/ANTLRLexer.java",
        "org/antlr/grammar/v3/ANTLRParser.java",
        "org/antlr/grammar/v3/ANTLRTreePrinter.java",
        "org/antlr/grammar/v3/ANTLRv3Lexer.java",
        "org/antlr/grammar/v3/ANTLRv3Parser.java",
        "org/antlr/grammar/v3/AssignTokenTypesWalker.java",
        "org/antlr/grammar/v3/CodeGenTreeWalker.java",
        "org/antlr/grammar/v3/DefineGrammarItemsWalker.java",
        "org/antlr/grammar/v3/LeftRecursiveRuleWalker.java",
        "org/antlr/grammar/v3/TreeToNFAConverter.java",
    ],
    cmd = select({
        "@bazel_tools//src/conditions:windows": """$(JAVA) -cp $(location @antlrtool352//jar);$(location @antlrruntime352//jar);$(location @stringtemplate4//jar) org.antlr.Tool -fo $(RULEDIR)/org/antlr/grammar/v3 $(SRCS)""",
        "//conditions:default":                 """$(JAVA) -cp $(location @antlrtool352//jar):$(location @antlrruntime352//jar):$(location @stringtemplate4//jar) org.antlr.Tool -fo $(RULEDIR)/org/antlr/grammar/v3 $(SRCS)""",
    }),
    tools = [
        "@antlrtool352//jar",
        "@antlrruntime352//jar",
        "@stringtemplate4//jar",
    ],
    toolchains = ["@bazel_tools//tools/jdk:current_java_runtime"],
)

java_library(
    name = "antlr3_tool",
    srcs = glob(["tool/src/main/**/*.java"]) + [":grammars"],
    resources = glob([
        "tool/src/main/resources/**",
        "tool/src/main/antr3/**",
    ]),
    javacopts = ["-XepDisableAllChecks"],
    deps = [
        "@stringtemplate3//jar",
        "@stringtemplate4//jar",
        ":antlr3_runtime",
    ],
)

java_library(
    name = "antlr3_runtime",
    srcs = glob(["runtime/Java/src/main/**/*.java"]),
    javacopts = ["-XepDisableAllChecks"],
    deps = [
        "@stringtemplate3//jar",
        "@stringtemplate4//jar",
    ],
)
