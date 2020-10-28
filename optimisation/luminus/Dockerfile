FROM clojure:lein-2.9.1

ADD project.clj project.clj

RUN exit | lein repl

RUN exit | lein with-profile +project/dev repl
